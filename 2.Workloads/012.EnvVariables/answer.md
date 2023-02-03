1. k run webapp-color --image=kodekloud/webapp-color --env="APP_COLOR=green" --labels="name=webapp-color" -o yaml --dry-run=client
  - check file1
2. check file2

## file2
```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    name: webapp-color
  name: webapp-color
spec:
  containers:
  - envFrom:
    - configMapRef:
        name: webapp-config-map
    image: kodekloud/webapp-color
    name: webapp-color
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

## file1
```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    name: webapp-color
  name: webapp-color
spec:
  containers:
  - env:
    - name: APP_COLOR
      value: green
    image: kodekloud/webapp-color
    name: webapp-color
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

```
apiVersion: v1
data:
  APP_COLOR: darkblue
kind: ConfigMap
metadata:
  name: webapp-config-map
  namespace: default

```