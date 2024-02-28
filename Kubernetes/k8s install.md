
## Step 1:

## On Master and Worker:

```bash
sudo apt-get update -y
sudo apt-get install docker.io -y
sudo service docker restart

sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" >/etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y
```

## Step 2:

## On Master node:

```bash
kubeadm init --pod-network-cidr=192.168.0.0/16
```

## Step 3:

## On Master node:

```bash
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

## Step 4:

## On Master node:

```bash
kubectl apply -f https://docs.projectcalico.org/v3.20/manifests/calico.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.49.0/deploy/static/provider/baremetal/deploy.yaml
```