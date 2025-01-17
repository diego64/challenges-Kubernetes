<p align="center">
  <img src="img.shields.io/image/kubernetes.png" width="500" alt="Capa" /></a>
</p>

## 📝 Challenge Day 07

The seventh challenge is to create different ways to make your application available through Services.

Services in Kubernetes are an abstraction that defines a logical set of Pods and a policy for accessing them. They allow you to expose one or more Pods to be accessed by other Pods, regardless of where they are running in the cluster.

Services are defined using the Kubernetes API, typically through a YAML manifest file.

Service Types

There are four main types of Services:

→ ClusterIP (default): Exposes the Service on an internal IP in the cluster. This type makes the Service accessible only within the cluster.

→ NodePort: Exposes the Service on the same port of each selected Node in the cluster using NAT. Makes the Service accessible from outside the cluster using :.

→ LoadBalancer: Creates an external load balancer in the current cloud environment (if supported) and assigns a fixed IP, external to the cluster, to the Service.

→ ExternalName: Maps the Service to the contents of the externalName field (for example, foo.bar.example.com), returning a CNAME record with its value.

---

## 📦️ Challenge

- [x] Create a ClusterIP service
- [x] Create a NodePort service
- [x] Create a NodePort LoadBalancer

---

## 📦️ Install

<h4>Installation is based on linux distributions</h4>

> 1. Applying the manifest files:
>
> ```console
> $ kubectl deployments.apps nginx
> $ kubectl apply -f nginx-clusterip-svc.yaml
> $ kubectl apply -f nginx-nodeport-svc.yaml
> $ kubectl apply -f nginx-loadbalancer-svc.yaml
> ```
>
> 2. Checking the services
> ```console
> $ kubectl get svc
> $ kubectl get pods
> $ kubectl get statefulsets
> ```