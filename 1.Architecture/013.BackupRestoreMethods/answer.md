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