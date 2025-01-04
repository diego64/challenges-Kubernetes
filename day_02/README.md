<p align="center">
  <img src="img.shields.io/image/capa.png" width="500" alt="Capa" /></a>
</p>

## 📝 Challenge Day 02

The objective of the second challenge is to create a Pod with two containers using different images and applying new concepts.

For this challenge, two Containers were created (frontend and api-server)

---

## 📦️ Challenge

- [x] Creating more than one container in a Pod
- [x] Hardware resource limitations (Memory and CPU)
- [x] Volume creation

---

### 🗃️ Command to execute the file

<h4>From <code>source</code></h4>

> 1. Clone the repository:
>
> ```console
> $ https://github.com/diego64/challenges-Kubernetes
> ```
>
> 2. List the pods
> ```console
> $ kubectl get all
> ```
>
> 3. Consult the pods
> ```console
> $ kubectl get pods frontend -o wide
> $ kubectl get pods server-api -o wide
> ```

---