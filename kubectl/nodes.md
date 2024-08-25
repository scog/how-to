## How To: kubectl commands for nodes

Helpful node-level operations for kubernetes using `kubectl`

---

### Drain & cordon a node
```bash
my_node="node1"                  # Set the name of the node you wish to drain and cordon

# First, drain all resources and delete temporary data local to the node
kubectl drain ${my_node} --ignore-daemonsets --delete-emptydir-data

# Next, cordon the node
kubectl cordon ${my_node}        

#
# Reboot the node as needed or perform maintenance on the node.
#

# To uncordon the node:
kubectl uncordon ${my_node}
``` 