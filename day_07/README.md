kubectl deployments.apps nginx
kubectl get pods
kubectl apply -f nginx-clusterip-svc.yaml
kubectl apply -f nginx-nodeport-svc.yaml
kubectl apply -f nginx-loadbalancer-svc.yaml
kubectl get svc
   
   
kubectl get statefulsets
kubectl delete statefulsets nome do statefulsets


nginx-clusterip-svc.yaml
nginx-deployment.yaml
nginx-headless-svc.yaml
nginx-loadbalancer-svc.yaml
nginx-nodeport-svc.yaml
statefulset-nginx.yaml

kubectl get svc
kubectl get pods
kubectl get statefulsets