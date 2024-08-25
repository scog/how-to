## How To: kubectl commands for pods

Helpful pod-level operations for kubernetes using `kubectl`

---

### Scaling StatefulSets
```bash
ns="my-namespace"         # Set your namespace

# Get list of StatefulSets
kubectl -n ${ns} get statefulsets

# Scale down the StatefulSet to ZERO replicas
kubectl -n ${ns} scale statefulset my-stateful-set --replicas=0

# Scale up the StatefulSet to ONE replicas
kubectl -n ${ns} scale statefulset my-stateful-set --replicas=1
```
