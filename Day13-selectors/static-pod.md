# The Schedular in the control plane is responsible for scheduling the pods in the nodes.
# The kubelet in the nodes is responsible for running the pods.
# The kube-scheduler is responsible for scheduling the pods in the nodes.

# But kube-scheduler is itself a pod that runs in the control plane.
# Static Pods -> Static pods are managed directly by the kubelet daemon on a specific node, rather than by the Kubernetes control plane's kube-scheduler.
# Each specific node has its own kubelet, which manages its static pods in the /etc/kubernetes/manifests directory.
# (A node is nothing but a docker container) 

# Lets take an example
# kube scheduler is a static pod... Now if remove kube-scheduler.yaml file from kubelet's manifest,
#                                  then there will be no assignment of pods to nodes and pod will enter into a pending state

# If we have to move pod from one node to another we have to delete it and recreate