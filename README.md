# ingress_hello_app
Use ingerss to access the hello-app through URL
This code is tested on minikube.
Before the deployment make sure:
Enable nginx ingress controller
minikube addons enable ingress
 Check the namespaces
kubectl get namespaces
![image](https://github.com/jaimindevops/ingress_hello_app/assets/115662244/55fa8271-f19f-4a46-bb44-3eb9a4cd56e5)

Than verify it's is running:
![image](https://github.com/jaimindevops/ingress_hello_app/assets/115662244/b0b0be38-b50c-40ed-9cf9-17fa39f5aa8a)

Than Deploy the Hello App application by using the deployment.yaml:
kubectl apply -f deployment.yaml

and than expose this deployment:
kubectl expose deployment ingress-demo --type=NodePort --port=8080
or can use the service.yaml file as:
kubectl apply -f service.yaml

Access the app via the node-ip and node-port,
Note: if minikube is deployed through wsl need to run the minikube tunnel command

Now apply the ingress manifest file:
kubectl apply -f ingress.yaml

verfiy the ingress: kubectl get ingress

update the cat /etc/hosts file with your cluster address
