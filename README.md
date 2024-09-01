# Jenkins Deployment on Kubernetes

#### Run Jenkins As a POD (Simple)
~~~
rm -rf k8s-jenkins
git clone https://github.com/SumonPaul18/k8s-jenkins.git
cd k8s-jenkins
kubectl apply -f jenkins-pod.yaml
kubectl get pod,pv,pvc
~~~
#### Port Forward to Jenkins-Pod
~~~
kubectl port-forward jenkins-pod 32000:8080 --address 0.0.0.0 &
~~~
#### Delete all to Jenkins-Pod
~~~
kubectl delete pod jenkins-pod
kubectl delete svc 
kubectl delete pvc 
kubectl delete pv 
~~~
#### Run Jenkins As a Deployment (Advanced)
~~~
rm -rf k8s-jenkins
git clone https://github.com/SumonPaul18/k8s-jenkins.git
cd k8s-jenkins/k8s-jenkins-deploy
kubectl apply -f .
kubectl get deploy,pod,svc,pv,pvc -n jenkins
~~~
