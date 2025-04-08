# Example Flux Repository

This repository is designed to work with a [kind](https://kind.sigs.k8s.io/) cluster and serve as an example for how Kollie can be used.

It assumes your cluster has been set up with port mappings for ports 80 and 443 so Ingress can work. For example:

```
cat <<EOF | kind create cluster --config=-
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
  - containerPort: 443
    hostPort: 443
    protocol: TCP
EOF
```
