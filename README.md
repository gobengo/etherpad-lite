# etherpad-lite

Configuration for running [Etherpad Lite](https://github.com/ether/etherpad-lite) on kubernetes.

`./lib/` contains several directories that configure Etherpad Lite in different ways, from the very simplest (but using ephemeral storage) to one that stores ether pads in MySQL provisioned by kubedb.

## Usage

Use `kubectl kustomize <dir>` to render kubernetes manifests, e.g.

```
kubectl kustomize lib/etherpad-lite-k8s
```

or

```
kubectl kustomize lib/etherpad-lite-k8s-kubedb-mysql/
```

or (via URL, no git clone required!)

```
kubectl kustomize github.com/gobengo/etherpad-lite.git/lib/etherpad-lite-k8s
```

## Install on Kubernetes

Assuming you have created a namespace named `my-etherpad-namespace` with something like `kubectl create ns my-etherpad-namespace`

```
kubectl kustomize github.com/gobengo/etherpad-lite.git/lib/etherpad-lite-k8s | kubectl apply -n my-etherpad-namespace -f -
```

If you don't have unix pipes:

```
kubectl -n my-etherpad-namespace apply -k github.com/gobengo/etherpad-lite.git/lib/etherpad-lite-k8s
```

