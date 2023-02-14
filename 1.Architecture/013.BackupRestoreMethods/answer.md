1. `kubectl -n kube-system logs etcd-controlplane | grep -i 'etcd-version'` and `kubectl -n kube-system describe pod etcd-controlplane | grep Image:`
2. `kubectl -n kube-system describe pod etcd-controlplane | grep '\--listen-client-urls'`
3. `kubectl -n kube-system describe pod etcd-controlplane | grep '.crt'`
4. see file 1
5. see file 2

```
ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 \
--cacert=/etc/kubernetes/pki/etcd/ca.crt \
--cert=/etc/kubernetes/pki/etcd/server.crt \
--key=/etc/kubernetes/pki/etcd/server.key \
snapshot save /opt/snapshot-pre-boot.db
```


```
ETCDCTL_API=3 etcdctl  --data-dir /var/lib/etcd-from-backup \
snapshot restore /opt/snapshot-pre-boot.db
```

1. `k config get-clusters`
2. follow
  1. kubectl config use-context cluster1
  2. k get nodes
3. kubectl get pods -n kube-system | grep etcd
4. follow
  1. ssh into node
  2. ps -ef | grep etcd
5. kubectl -n kube-system describe pod etcd-cluster1-controlplane | grep data-dir
6. ps -ef | grep etcd
7. see file3
8. see file 4
9. see file 5

file3
```
ETCDCTL_API=3 etcdctl \
 --endpoints=https://127.0.0.1:2379 \
 --cacert=/etc/etcd/pki/ca.pem \
 --cert=/etc/etcd/pki/etcd.pem \
 --key=/etc/etcd/pki/etcd-key.pem \
  member list
```

file 4
```
# switch to cluster1
kubectl config use-context cluster1

# check etcd detail
kubectl describe  pods -n kube-system etcd-cluster1-controlplane  | grep advertise-client-urls

# check cert
kubectl describe  pods -n kube-system etcd-cluster1-controlplane  | grep pki

# backup
ETCDCTL_API=3 etcdctl --endpoints=https://10.1.220.8:2379 --cacert=/etc/kubernetes/pki/etcd/ca.crt --cert=/etc/kubernetes/pki/etcd/server.crt --key=/etc/kubernetes/pki/etcd/server.key snapshot save /opt/cluster1.db

```

file 5
