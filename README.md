# Jenkins Deployment on Kubernetes

### Run Jenkins As a POD (Simple)
~~~
rm -rf k8s-jenkins
git clone https://github.com/SumonPaul18/k8s-jenkins.git
cd k8s-jenkins
kubectl apply -f jenkins-pod.yaml
kubectl get pod,pv,pvc
~~~
#### Port Forwarding to Jenkins-Pod
~~~
kubectl port-forward jenkins-pod 32000:8080 --address 0.0.0.0 &
~~~
#### Delete all to Jenkins-Pod
~~~
kubectl delete pod jenkins-pod 
kubectl delete pvc jenkins-nfs-pvc
kubectl delete pv jenkins-nfs-pv
~~~
#### Delete Port Forwarding to Jenkins-Pod
~~~
ps -ef | grep port-forward | grep 32000 | awk '{print $2}'
kill -9 [PID]
~~~
#
### Run Jenkins As a Deployment (Advanced)
~~~
rm -rf k8s-jenkins
git clone https://github.com/SumonPaul18/k8s-jenkins.git
cd k8s-jenkins/k8s-jenkins-deploy
kubectl apply -f .
kubectl get deploy,pod,svc,pv,pvc -n jenkins
~~~
#### Delete all to Jenkins-Deploy
~~~
kubectl delete ns jenkins
kubectl delete pvc jenkins-nfs-pvc
kubectl delete pv jenkins-nfs-pv
~~~
