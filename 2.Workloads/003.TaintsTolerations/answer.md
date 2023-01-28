1. `k taint nodes node01 spray=mortein:NoSchedule`
2. use `k run` create yaml file and add `tolerations` under `spec`
3. `kubectl taint nodes controlplane node-role.kubernetes.io/control-plane:NoSchedule-`