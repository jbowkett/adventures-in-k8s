# adventures-in-k8s

To create a service:
1. docker image build .
1. minikube dashboard &
1. kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node
1. kubectl get deployments
1. kubectl expose deployment hello-node --type=LoadBalancer --port=8080
1. kubectl get services
1. minikube service hello-node

