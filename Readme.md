KUBERNETES COMMANDS

docker build -t kub-first-app . 
kubectl create deployment first-app --image=kub-first-app  

kubectl get deployment 


kubectl delete deployment first-app


go and create a repo in docket hub with name sub-first-app
docker tag kub-first-app sayinmehmet47/kub-first-app
docker push sayinmehmet47/kub-first-app 

kubectl create deployment first-app --image=sayinmehmet47/kub-first-app
kubectl get deployments
kubectl get pods


minikube dashboard   


//service creating
kubectl expose deployment first-app --type=LoadBalancer --port=8080


minikube service first-apps

// change the route to /error and than look at the pods status
kubectl get pods




SCALING

kubectl scale deployment/first-app --replicas=3

change the route to /error and look at the pods in kubernetes dasboard



kubectl scale deployment/first-app --replicas=1

UPDATE DEPLOYMENTS
docker build -t sayinmehmet47/kub-first-app .

//send change to dockethub
docker push sayinmehmet47/kub-first-app  
kubectl set image deployment/first-app kub-first-app=sayinmehmet47/kub-first-app
above one will not make change since we did not change the version of docket image when build it

// docker build -t sayinmehmet47/kub-first-app:2 .  
 docker push sayinmehmet47/kub-first-app:2 
kubectl rollout status deployment/first-app  

LOOK AT THE HISTORY
kubectl rollout history deployment/first-app

DECLERATIVE METHOD
kubectl apply -f deployment.yaml
minikube service backend(service name is backend in our usacase)


CHANGE REPLICAS AND PODS AND DEPLOY AGAIN



MERGE THE SERVICES AND DEPLOYMENT


SEND THE LAST CHANGES AND GRAB THEM WITH IMAGE POLICY ALWAYS

docker build -t sayinmehmet47/kub-first-app:2 .
docker push sayinmehmet47/kub-first-app:2  
 kubectl apply -f=masterdeployment.yaml
docker build -t sayinmehmet47/kub-first-app:2 .
docker push sayinmehmet47/kub-first-app:2  
kubectl delete  -f=masterdeployment.yaml 
