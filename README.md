This project deploys a web application to a Kubernetes cluster 

I used the MongoDB image and a Node webapp image already on Docker hub.

Four Config files were created for this project
- ConfigMap for MongoDB Endpoint
- Secret for MongoDB UserName and Password
- Deployment and Service for MongoDB with internal service
- Deployment and Service for webapp with external service configuration to enable external access through the internet browser

In order to deploy the resourses on Kubernetes cluster, I used the following command to create the configMap and secret component first

To create a ConfigMap
` kubectl apply -f mongo-config.yaml `

To create a Secret
` kubectl apply -f mongo-secret.yaml `

To create the Database
` kubectl apply -f mongo.yaml `

To create the webapp
` kubectl apply -f webapp.yaml `

#### To interract with the Minikube 

```
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all
```
To get extended info about components
```
kubectl get pod -o wide
kubectl get node -o wide
```

#### To get detailed info about a specific component
```
kubectl describe svc {svc-name}
kubectl describe pod {pod-name}
```

#### To get application logs
` kubectl logs {pod-name} `

#### To check Minikube status
` minikube status `

#### To get minikube node's ip address
` minikube ip `

#### To access the webapp from the terminal
` minikube service webapp-service `

#### To stop minikube
` minikube stop `

#### Links
```
mongodb image on Docker Hub: https://hub.docker.com/_/mongo

webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app

k8s official documentation: https://kubernetes.io/docs/home/

webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour
```
