kubectl create namespace quote-of-the-day-app
kubectl get all -n quote-of-the-day-app

kubectl apply -f mysql-secret.yaml 
kubectl apply -f mysql-persistent-volume.yaml 
kubectl apply -f mysql-deployment.yaml
kubectl apply -f mysql-service.yaml
CREATE THE TABLE ### for now I am creating the table manually , but this need to be fixed. Script is init.sql
kubectl exec -it quote-mysql-0 -n quote-of-the-day-app -- bash
mysql -u admin -p

kubectl apply -f quote-app-deployment.yaml
kubectl apply -f quote-app-service.yaml

