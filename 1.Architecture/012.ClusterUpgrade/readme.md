# Cluster Upgrade

 - CKA
    - Cluster Architecture
    - Claster Maintenance
    - Cluster Upgrade

1. What is the latest stable version of Kubernetes as of today?
2. We will be upgrading the controlplane node first. Drain the controlplane node of workloads and mark it UnSchedulable
3. Upgrade the controlplane components to exact version v1.26.0 [^1] [^2]
4. Mark the controlplane node as "Schedulable" again

[^1]: Upgrade the kubeadm tool (if not already), then the controlplane components, and finally the kubelet. Practice referring to the Kubernetes documentation page.
[^2] Note: While upgrading kubelet, if you hit dependency issues while running the apt-get upgrade kubelet command, use the apt install kubelet=1.26.0-00 command instead.


