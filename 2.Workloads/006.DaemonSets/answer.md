1. file 

```
apiVersion: apps/v1
kind: DaemonSet
metadata:
  namespace: kube-system
  name: elasticsearch
  labels:
    app: elasticsearch
spec:
  revisionHistoryLimit: 10
  selector:
    matchLabels:
      app: elasticsearch
  template:
    metadata:
      labels:
        app: elasticsearch
    spec:
      containers:
      - image: registry.k8s.io/fluentd-elasticsearch:1.20
        name: fluentd-elasticsearch


```