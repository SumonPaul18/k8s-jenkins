# Jenkins Deployment on Kubernetes

#### Clone Repository
~~~
rm -rf k8s-jenkins
git clone https://github.com/SumonPaul18/k8s-jenkins.git
cd k8s-jenkins
kubectl apply -f .
kubectl get deploy,pod,svc,pv,pvc -n jenkins
~~~
