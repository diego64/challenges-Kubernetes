<p align="center">
  <img src="img.shields.io/image/capa.png" width="500" alt="Capa" /></a>
</p>

## 📝 Challenge Day 03

The goal of the fourth challenge is to create YAML files with specific declarations according to each request.

---

## 📦️ Challenge

- [x] Create a deployment with limited consumption resources (CPU and Memory)
- [x] Create a file with deployment strategy
- [x] Create a file with Probe
- [x] Create a file gathering all the strategies from the previous items (Bonus Personal)

---

### 🗃️ Execution | To execute each file, simply run the commands, changing only the file names.

<h4>From <code>source</code></h4>

> 1. Clone the repository:
>
> ```console
> $ https://github.com/diego64/challenges-Kubernetes
> ```
>
> 2. Create a group called day03
> ```console
> $ cd challenges-Kubernetes/day_04
> ```
>
> 3. Run the file
> ```console
> $ kubectl apply -f <file-name>.yaml
> $ kubectl describe deployment <file-name>
> ```
> 4. Commands to check the status of file creation
> ```console
> $ kubectl get pods -n <file-name>.yaml
> $ kubectl describe node
> ```
> 5. Use the rollout in the file
> ```console
> $ kubectl rollout history deployment <file-name> -n <namespace>
> $ kubectl rollout history deployment <file-name> -n <namespace> --revision=2
> ```
> 5. Rollback Command
> ```console
> $ kubectl rollout undo deployment -n <file-name> -n <namespace>
> ```
> 6. To delete all created pods, simply run the command
> ```console
> $ kubectl delete pods --all -n <namespace>
> ```