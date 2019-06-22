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
