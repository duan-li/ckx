1. Look at the `remote version` in the output of the `kubeadm upgrade plan`.
2. `kubectl drain controlplane --ignore-daemonsets`
3. check file1
4. kubectl uncordon controlplane

```
apt update
apt-get install kubeadm=1.26.0-00
kubeadm upgrade apply v1.26.0
apt-get install kubelet=1.26.0-00 
systemctl daemon-reload
systemctl restart kubelet
```


