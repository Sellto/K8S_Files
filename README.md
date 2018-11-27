# K8S_Files

## node-labeler-rbac.yaml
composed by 3 items :
- creation of the *node-labeling* namespaces
- creation of a clusterrole that give the right to lablise the nodes but don't list them.
- creation of a clusterrolebinding to bind the namespaces with the clusterrole.

It is used with a auto-labelise service. When a device is plugged into a nodes, it can labelise himself with the description of this new component.

To confine this service, we launch it into the node-labeling namespaces which has only the right to change or update the label of the nodes, but don't list them. Normally with this technique a node can't find the name of the other nodes and therefore labelise a other nodes as himself.
