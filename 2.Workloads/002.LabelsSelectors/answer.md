1. `k get pod --selector env=dev`
2. `k get pod --selector bu=finance`
3. `kubectl get all --selector env=prod --no-headers | wc -l`
  * `k get all --selector env=prod`
4. `k get pod --selector env=prod,bu=finance,tier=frontend`
