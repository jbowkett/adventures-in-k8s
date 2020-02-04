# adventures-in-k8s

## To create a service:
1. docker image build .
1. minikube dashboard &
1. kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node 
1. kubectl get deployments
1. kubectl expose deployment hello-node --type=LoadBalancer --port=8080
1. kubectl get services
1. minikube service hello-node

## To clean up:

1. kubectl delete service hello-node
1. kubectl delete deployment hello-node
1. minikube stop


## Useful Commands
1. minikube kubectl  - if the version of kubectl shipped with Docker is different to minikube's
1. minikube dashboard &
1. kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node --service - creates a service at the same time
1. kubectl get events
1. kubectl get deployments - this needs to read 1/1 if the deployment was successful
1. kubectl get pods
1. kubectl config view
1. kubectl proxy     - gives you access to your running pod, (if not running as a service)
1. kubectl get       - list resources
1. kubectl describe  - show detailed information about a resource
1. kubectl logs      - print the logs from a container in a pod
1. kubectl exec      - execute a command on a container in a pod
1. export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
1. kubectl exec $POD_NAME env
1. kubectl exec -ti $POD_NAME bash     -interactive shell on the pod itself
1. export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
1. curl $(minikube ip):$NODE_PORT
1. kubectl describe deployment
1. kubectl get services -l run=kubernetes-bootcamp
1. kubectl get rs    -replica set
1. kubectl scale deployments/kubernetes-bootcamp --replicas=4   -scale to 4 replicas 
1. kubectl get pods -o wide
1. kubectl describe deployments/kubernetes-bootcamp

