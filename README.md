# DEMO_K8s_configuration_file
 a simple DEMO  first K8s small project using YAML configuration file 

 22.03  Create pods ,deployment with prepared with k8s configuration files 
24.03.2025

*minikube and kubectl installed  up and running , selected environment :Hyper-v
-------------------------------------------------------------------------------------
we now create one by one each component in K8s:
$kubectl get pod
No resources found in default namespace.
to crate pods:
kubectl apply -f mongo-config.yml
kubectl apply -f mongo-secret.yml
kubectl apply -f mongo.yml 
kubectl apply -f webapp.yml
PS C:\Users\mmb20\OneDrive\Desktop\k8s\k&s-DEMO> kubectl get all 
kubectl get pod
NAME READY STATUS RESTARTS AGE
mongo-deployment-7495d4cf4b-9fq4v 1/1 Running 0 88s
webapp-deployment-7c44bc5b56-mtld4 1/1 Running 0 77s

kubectl get all
we can see all deployments, service and etc 
NodePort    10.102.59.222   <none>        8080:30100/TCP   14m
means we can access it external !




kubectl get configmap


FROM EXTERNAL OR BROWSER 
$kubectl get pod, then we can see the port its listening, kubectl logs “pod name”

kubectl logs  (pad's name )webapp-deployment-7c44bc5b56-mtld4
INFO: Will watch for changes in these directories: ['/code']
INFO: Uvicorn running on http://0.0.0.0:8080 (Press CTRL+C to quit)
INFO: Started reloader process [1] using StatReload
INFO: Started server process [8]


$kubectl get svc
NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE
kubernetes ClusterIP 10.96.0.1 <none> 443/TCP 19m
mongo-service ClusterIP 10.111.225.76 <none> 27017/TCP 16m
webapp-service NodePort 10.105.190.6 <none> 8080:30100/TCP 16m


minikube ip
172.26.235.187

Browser: minikubeip:172.26.237.16:30100
http://172.26.235.187:30100/
# DONEEEE 24.03.
we do not need to run anything, minikube is running 
---------------------------------------------------------------------------------------------------------------


