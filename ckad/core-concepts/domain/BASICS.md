### Basics

A `kubernetes cluster` consists of a set of `worker nodes`, inside of the nodes we deploy application components as `PODs`. All the nodes and PODs are managed by the `Control Plane` components.

### Control Plane

Consists of multiple components such:

- `kube-apiserver`: The API server exposes REST interface to the kubernetes cluster.
  All the operations against `pods`, `services`, and so forth, are executed programmatically
  by communicating with the endpoints provided by it.

- `etcd`: a distributed key-value store that kubernetes uses to share information about the overall state of a cluster.

- `kube-scheduler`: responsible for assigning work to the various nodes. It keeps watching over the resources capacity and ensures that a worker node's performance is within an appropriate threshold.

- `kube-controller-manager`: control plane component that runs controller processes. These controllers include `Node Controller`, `Replication Controller`, `Deployment Controller` `Endpoints Controller`, `Service Account & Token Controller` ...

- `kubelet`: agent that runs on each node in the cluster. The `kubelet`takes a set of `PodSpecs` that are provided through various mecanisms and ensures that the containers described in those `PodsSpecs` are running and healthy.

- `kube-proxy`: is a network proxy that runs on each node in your cluster, implementing part of the `Kubernetes Service` concept. `kube-proxy` mantain network rules on nodes

- `Container Runtime`: Kubernetes supports several containers runtimes such `Docker`, `containerd`, `CRI-O` and any implementtion of the Kubernetes CRI (Container Runtime Interface)
