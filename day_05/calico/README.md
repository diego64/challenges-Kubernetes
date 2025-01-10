<p align="center">
  <img src="../img.shields.io/image/kubernetes.png" width="500" alt="Capa" /></a>
</p>

## 📝 Installing a Kubernetes cluster using Kubeadm with Calico networking mode

Calico is one of the most popular and widely used networking plugins in Kubernetes. It provides network security and allows you to enforce network policies. Calico uses BGP (Border Gateway Protocol) to route traffic between cluster nodes, providing efficient and scalable performance.

---

## 📦️ Install

<h4>Installation is based on linux distributions</h4>

> 1. Update packages on the system::
>
> ```console
> $ sudo apt update && sudo apt upgrade -y
> ```
>
> 2. Disable Swap
> ```console
> $ sudo swapoff -a
> $ sed -i '/ swap / s/^/#/' /etc/fstab
> ```
>
> 3. Configure Kernel Parameters for Kubernetes:
> ```console
> $ cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf
> overlay
> br_netfilter
> EOF
> $
> $ cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
> $ sudo modprobe br_netfilter
> net.bridge.bridge-nf-call-iptables = 1
> net.bridge.bridge-nf-call-ip6tables = 1
> net.ipv4.ip_forward = 1
> EOF
> $
> $ sudo sysctl --system
> ```
>
> 4. Install Docker as a container runtime:
> ```console
> $ sudo apt install -y docker.io
> $ sudo systemctl enable docker
> $ sudo systemctl start docker
> ```
> 5. Add the Kubernetes repository
> ```console
> $ sudo apt update
> $ sudo apt install -y apt-transport-https ca-certificates curl
> $ curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
> $ cat <<EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
> deb https://apt.kubernetes.io/ kubernetes-xenial main
> EOF
> $ sudo apt update
> ```
> 6. Install the required packages
> ```console
> $ sudo apt install -y kubelet kubeadm kubectl
> $ sudo apt-mark hold kubelet kubeadm kubectl
> ```
> 7. To delete all created pods, simply run the command
> ```console
> $ sudo kubeadm init --pod-network-cidr=192.168.0.0/16
> ```
> 8. Configure Kubernetes for the current user
> ```console
> $ mkdir -p $HOME/.kube
> $ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
> $ sudo chown $(id -u):$(id -g) $HOME/.kube/config
> ```
> 9. Install a Network Plugin (CNI)
> ```console
> $ kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
> ```
> 10. Install a Network Plugin (CNI)
> ```console
> $ kubeadm join 192.168.0.0:6443 --token <TOKEN> --discovery-token-ca-cert-hash sha256:<HASH>
> ```
> 11. Verify the Cluster
> ```console
> $ kubectl get nodes
> $ kubectl get pods --all-namespaces
> ```

> 11. Test Cluster
> ```console
> $ kubectl create deployment nginx --image=nginx
> $ kubectl expose deployment nginx --type=NodePort --port=80
> $ kubectl get svc
> ```