1. `kubectl exec webapp -- cat /log/app.log`
2. given properties under the `spec.volumes` and `spec.containers.volumeMounts`. 
3. see file 3


# file 2
```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: webapp
  name: webapp
spec:
  containers:
  - image: kodekloud/event-simulator
    name: webapp
    volumeMounts:
    - mountPath: /log
      name: log-volume
  dnsPolicy: ClusterFirst
  restartPolicy: Always
  volumes:
  - name: log-volume
    hostPath:
      path: /var/log/webapp
      type: Directory
```





# file 3

## by myself
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-log
spec:
  persistentVolumeReclaimPolicy: Retain
  accessModes: 
    - ReadWriteMany
  capacity:
     storage: 100Mi
  hostPath:
    path: /pv/log
  
```

## by answer
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-log
spec:
  persistentVolumeReclaimPolicy: Retain
  accessModes:
    - ReadWriteMany
  capacity:
    storage: 100Mi
  hostPath:
    path: /pv/log
   
```