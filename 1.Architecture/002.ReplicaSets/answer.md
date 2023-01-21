1. k get ReplicaSets / k get rs
2. k describe rs, then k describe pod.
3. kubectl explain replicaset | grep VERSION
4. k create -f file.yaml
5. kubectl scale rs new-replica-set --replicas=5 
  - k edit rs rs-name


## check issue
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: replicaset-2
spec:
  replicas: 2
  selector:
    matchLabels:
      tier: nginx
  template:
    metadata:
      labels:
        tier: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
```