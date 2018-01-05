Install Minikube:

https://kubernetes.io/docs/tasks/tools/install-minikube/

Tag the image to get it ready to push to docker hub

docker tag my_react_nginx ziaukhan/nginx-react:step03

docker push ziaukhan/nginx-react:step03

Now it is available at https://hub.docker.com/r/ziaukhan/nginx-react/tags/

Now start minikube:

minikube start

Check to see if the cluster is up and running:

kubectl cluster-info

Check to see one node is running:

kubectl get nodes

Get full info about the node:

kubectl describe node minikube

To create the deployment:

kubectl create -f deployment.yaml --record

To see the status of the deployment:

kubectl rollout status deployment nginx-react-deployment

To check and see if ReplicaSet was created sucessfully:

kubectl get rs

To check and see if the three pods are up and running (it will take a few moments):

kubectl get pods

To see the labels on the pods:

kubectl get po --show-labels

Now create a loadbalancer service so that we can access from outside the cluster:

kubectl create -f service.yaml

To get the external IP address:

kubectl get svc nginx-react-loadbalancer

As we are using Minikube, even though the load balancer will never be
provisioned, you can still access the service through the node port (at the
Minikube VM’s IP address)

To get the IP address of the Minikube:

minikube ip

Now your home work is to connect to the loadbalancer service locally thorough your browser.






