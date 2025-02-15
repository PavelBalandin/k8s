# Kubernetes ⎈ 

## Install Kubernetes 

#### Windows
https://medium.com/@javatechie/kubernetes-installation-guide-windows-mac-f65105146127
#### Mac
https://medium.com/@javatechie/kubernetes-tutorial-install-run-minikube-in-mac-os-k8s-cluster-369b25b0c3f0

## Get started with an example

### Plain Kubernetes manifests

Create a Namespace (Optional)

`kubectl create namespace rabbitmq`

Create a deployment for RabbitMQ (example already created). Apply the deployment with:

`kubectl apply -f rabbitmq-deployment.yaml`

Create a service for RabbitMQ (example already created). Apply the service with:

`kubectl apply -f rabbitmq-service.yaml`

Forward the RabbitMQ management port to your local machine

`kubectl port-forward svc/rabbitmq 15672:15672 5672:5672`

`kubectl --namespace rabbitmq port-forward svc/rabbitmq 15672:15672 5672:5672`

### Helm
Install Helm
https://helm.sh/docs/intro/install/

Create a Namespace (Optional)

`kubectl create namespace rabbitmq`

Add the Bitnami repository (which includes RabbitMQ Helm charts)

`helm repo add bitnami https://charts.bitnami.com/bitnami`

Update the Helm repositories to make sure you have the latest version

`helm repo update`

Install and run RabbitMQ with default configurations

`helm install rabbitmq bitnami/rabbitmq --set auth.username=guest --set auth.password=guest --namespace rabbitmq`

Forward the RabbitMQ management port to your local machine

`kubectl --namespace rabbitmq port-forward svc/rabbitmq 15672:15672 5672:5672`

For uninstall helm release

`helm uninstall rabbitmq`


## Commands for Managing Kubernetes

#### Minikube

`minikube start`

`minikube status`

`minikube stop`

`minikube delete`


#### Kubectl
`kubectl cluster-info`

`kubectl get nodes`

`kubectl describe node minikube`

`kubectl get namespaces`

`kubectl create namespace <namespace-name>`

`kubectl config set-context --current --namespace=<namespace-name>`

`kubectl get pods`

`kubectl get pods -n <namespace>`

`kubectl describe pod <pod-name>`

`kubectl logs <pod-name>`

`kubectl exec-it <pod-name> -- bash`

`kubectl delete pod <pod-name>`

#### Helm
`helm list`

`helm install <release-name> <chart-name>`

`helm upgrade <release-name> <chart-name>`

`helm rollback <release-name> <revision>`

`helm uninstall <release-name>`