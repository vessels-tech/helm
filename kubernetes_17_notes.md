# Kubernetes 17 notes 
Notes on how to get this working with kubernetes 17

```bash
git clone git@github.com:vessels-tech/helm.git && cd helm
# git checkout fix/219-kubernetes-17
git checkout fix/219-kubernetes-17-helm2-2

./package.sh

# Figure out how to deploy helm locally
kubectl create namespace mojaloop

# in separate session, start a python server to serve charts locally
cd helm/repo
python3 -m http.server

# Tell helm we are using k3s, this will be different for your environment
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
helm install mojaloop http://localhost:8000/mojaloop-9.3.0.tgz

# TODO: ingress



# TODO: tests etc.

# TODO: Need to make the namespace first!
helm --namespace kube-public install stable/nginx-ingress

```