<p align="center">
  <img src="img.shields.io/image/capa.png" width="500" alt="Capa" /></a>
</p>

<p align="center">
	Developed with the software and tools below.
</p>

<p align="center">
    <img src="img.shields.io/badge/devops.svg?style=flat&logo=devops&logoColor=white" alt="devops.svg">
    <img src="img.shields.io/badge/kubernetes.svg?style=flat&logo=kubernetes&logoColor=white" alt="kubernetes">
    <img src="img.shields.io/badge/kind.svg?style=flat&logo=kind&logoColor=white" alt="kind">
    <img src="img.shields.io/badge/nginx.svg?style=flat&logo=nginx&logoColor=white" alt="nginx">
</p>

## 📝 Challenge Day 01

The objective of this challenge is to put into practice the knowledge obtained in the first chapter of the course Descomplicando o Kubernetes 2024 in which the basic concepts of Kubernetes were taught.

---

## 📦️ Challenge

- [x] Create a cluster with one node and 3 workers
- [x] Deploy a Pod with Nginx
- [x] The file name must be myfirstcluster.yaml

---

## 🏷️ Requirements to run the application

I will leave the link that shows the step by step installation of the tools for Linux, Windows and Mac: https://github.com/badtuxx/CertifiedContainersExpert/blob/main/DescomplicandoKubernetes/day-1/README.md

---

### 🗃️ Executing files Deploy

<h4>From <code>source</code></h4>

> 1. Clone the repository:
>
> ```console
> $ https://github.com/diego64/challenges-Kubernetes
> ```
>
> 2. Executing the deploynginx.yaml file
> ```console
> $ kubectl apply -f dedploynginx.yaml
> ```
>
> 3. File application
> ```console
> $ kubectl apply -f dedploynginx.yaml
> ```
> 4. Pod Verification
> ```console
> $ kubectl get pods
> ```

---

### 🗃️ Cluster execution

> 1. Find error in .yaml file:
>
> ```console
> $ yamllint meuprimeirocluster.yaml
> ```
>
> 2. Executing the .yaml file
> ```console
> $ kind create cluster --config meuprimeirocluster.yaml --name meuprimeiropod
> ```
>
> 3. Nodes Verification
> ```console
> $ kubectl get nodes
> ```
>
> 4. File application
> ```console
> $ kubectl apply -f meuprimeirocluster.yaml
> ```
---