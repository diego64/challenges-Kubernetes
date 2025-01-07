<p align="center">
  <img src="img.shields.io/image/capa.png" width="500" alt="Capa" /></a>
</p>

## 📝 Challenge Day 03

The objective of this challenge is to apply Deployment, Rollback and Rollout strategies through a manifest file.

---

## 📦️ Challenge

- [x] Create a group called day03
- [x] Create a group called day03-rc
- [x] Make an archive with the RollingUpdate strategy
- [x] Make an archive with the Recreate strategy

---

### 🗃️ Commands for the file configured in rollingUpdate.yaml

<h4>From <code>source</code></h4>

> 1. Clone the repository:
>
> ```console
> $ https://github.com/diego64/challenges-Kubernetes
> ```
>
> 2. Create a group called day03
> ```console
> $ kubectl create namespace day03
> $ kubectl get namespaces
> ```
>
> 3. Run the rollingUpdate.yaml file
> ```console
> $ kubectl apply -f rollingUpdate.yaml -n day03
> $ kubectl describe deployment challenge-ru -n day03
> ```
> 4. Commands to check the status of file creation
> ```console
> $ kubectl apply -f rollingUpdate.yaml -n day03
> $ kubectl get pods -n day03
> $ kubectl describe node
> ```
> 5. Use the rollout in the file
> ```console
> $ kubectl rollout history deployment challenge-ru -n day03
> $ kubectl rollout history deployment challenge-ru -n day03 --revision=2
> ```
> 5. Rollback Command
> ```console
> $ kubectl rollout undo deployment -n challenge-ru -n day03
> ```
> 6. To delete all created pods, simply run the command
> ```console
> $ kubectl delete pods --all -n day03
> ```

## 🚧 Commands for the file configured in recreate.yaml

For this file, just run the same command, just changing and applying the new group.
---