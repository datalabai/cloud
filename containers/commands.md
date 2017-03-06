# kubernetes

## minikube
minikube start
minikube status
minikube ip
minikube stop

## k8
k8 get nodes
k8 get deployments
k8 get rs (replica sets)
k8 get pods --show-labels

k8 describe deployments

k8 delete pod <pod-id>

k8 get namespaces
k8 create namespace jenkins
k8 delete namespace jenkins

k8 create secret
k8 create secret generic jenkins --from-file=<file> --namespace=<namespace>

## update a deployment
kubectl edit deployment/hello-node
kubectl rollout status deployment/hello-node


## helm
helm init
helm repo update
helm create stable/jenkins

## References
* https://cloud.google.com/solutions/jenkins-on-container-engine

## Steps
* cloud compute images create jenkins-home-image --source-uri https://storage.googleapis.com/solutions-public-assets/jenkins-cd/jenkins-home-v2.tar.gz
* cloud compute disks create jenkins-home --image jenkins-home-image

PASSWORD=`openssl rand -base64 15`; echo "Your password is $PASSWORD"; sed -i.bak s#CHANGE_ME#$PASSWORD# jenkins/k8s/options
