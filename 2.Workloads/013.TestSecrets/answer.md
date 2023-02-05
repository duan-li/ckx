1. kubectl create secret generic db-secret --from-literal=DB_Host=sql01 --from-literal=DB_User=root --from-literal=DB_Password=password123
2. k run webapp-pod --image=kodekloud/simple-webapp-mysql -o yaml --dry-run=client

```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: webapp-pod
  name: webapp-pod
spec:
  containers:
  - image: kodekloud/simple-webapp-mysql
    name: webapp-pod
    envFrom: 
    - secretRef:
        name: db-secret
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```