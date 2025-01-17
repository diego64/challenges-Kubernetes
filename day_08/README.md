<p align="center">
  <img src="img.shields.io/image/kubernetes.png" width="500" alt="Capa" /></a>
</p>

## 📝 Challenge Day 08

In this eighth challenge the objective is to apply a security certificate to the Cluster

---

## 📦️ Challenge

- [x] Install Kubernetes cluster using Kubeadm
- [x] Use different network plugins

---

## 🔨 Requirements

Hardware:

At least 2 machines (1 Master and 1 Worker), with at least:
2 CPUs
2 GB of RAM
Connection between machines.

Compatible Operating Systems: Ubuntu, CentOS or Debian (recommended to use recent versions).

Dependencies:
Internet connection to download packages.
IP forwarding control enabled in the kernel.
Swap disabled.

Tools to install:
Docker or another Kubernetes-compatible runtime.
Kubeadm, Kubelet and Kubectl.

---

## 📦️ Install

<h4>Installation is based on linux distributions</h4>

> 1. Create a Secret, the Base64 (This will give a result)
>
> ```console
> $ echo -n 'suachave' | base64
> ```
>
> 2. To decode a string into Base64
> ```console
> $ echo -n <resultado> | base64 -d
> ```
>
> 2.1. To create the secret
> ```console
> $ kubectl create secret generic nome-secret --from-literal=username=<SEGREDO> --from-literal=password=nome
> ```
>
> 3. Create a pod with the secret
> ```console
> $ kubectl apply -f pod-secret.yaml
> $ kubectl get pods ou kubectl exec giropops-pod -- env
> ```
> 4. Creating a Secret to store Docker credentials
> ```console
> $ doker login
> $ base64 ~/.docker/config.json
> $ kubectl apply -f dockerhub-secret.yaml
> $ kubectl get secrets
> ```
> 5. Creating a TLS Secret
> ```console
> $ openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout chave-privada.key -out certificado.crt
> $ kubectl create secret tls meu-servico-web-tls-secret --cert=certificado.crt --key=chave-privada.key
> $ secret/meu-servico-web-tls-secret created ou kubectl get secret meu-servico-web-tls-secret -o yaml
> ```
> 6. ConfigMaps
> ```console
> $ kubectl apply -f nginx-config.yaml
> $ kubectl get pods
> ```