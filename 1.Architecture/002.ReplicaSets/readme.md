# Basic ReplicaSets

 - CKA
    - Cluster Architecture
    - ReplicaSets

1. how many ReplicaSets
2. how to check why rs is not working.
3. get resource version
4. create rs from yaml file.
5. extend rs pod from 4 to 5

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
      tier: frontend
  template:
    metadata:
      labels:
        tier: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
```