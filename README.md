WordPress task: 
Create a ReplicaSet with 2 replicas, which runs WordPress 
And attach it to MySQL ReplicaSet on a Persistent Volume 
Expose WordPress through LoadBalancer service. Once done push yaml configurations for all resources you have created to GitHub P.S. MySQL setup will require a password, do not use any of your actual password you use with your other accounts, keep it simple like “password: password” 

  kubectl create -f wordpress-mysql-rs.yaml 
  kubectl create -f mysql-pvc.yaml 
  kubectl create -f wordpress-lb.yaml 
  kubectl create -f pvc.yaml 
  kubectl create -f pv.yaml 
  kubectl create -f deployment-wordpress.yaml 
  kubectl create -f headless.yaml "wordpress should work without headless" 

kubectl get services -o wide 
kubectl get pods -o wide
kubectl get nodes -o wide 
kubectl get rs -o wide 
 kubectl get pods --show-labels 
