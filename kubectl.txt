
Default:

root@instance-20240602-125323:~# kubectl get nodes
NAME                       STATUS   ROLES           AGE   VERSION
instance-20240602-125323   Ready    control-plane   39m   v1.29.0
instance-20240602-125903   Ready    <none>          38m   v1.29.0
instance-20240602-125931   Ready    <none>          38m   v1.29.0


Add Role
kubectl label node <node name> node-role.kubernetes.io/<role name>=<key - (any name)>



kubectl label node instance-20240602-125931 node-role.kubernetes.io/worker-1=w1

root@instance-20240602-125323:~# kubectl get nodes
NAME                       STATUS   ROLES           AGE   VERSION
instance-20240602-125323   Ready    control-plane   42m   v1.29.0
instance-20240602-125903   Ready    <none>          42m   v1.29.0
instance-20240602-125931   Ready    worker-1        42m   v1.29.0


kubectl label node instance-20240602-125903 node-role.kubernetes.io/worker-2=w2

root@instance-20240602-125323:~# kubectl get nodes
NAME                       STATUS   ROLES           AGE   VERSION
instance-20240602-125323   Ready    control-plane   43m   v1.29.0
instance-20240602-125903   Ready    worker-2        42m   v1.29.0
instance-20240602-125931   Ready    worker-1        42m   v1.29.0

Remove Role

kubectl label node <node name> node-role.kubernetes.io/<role name>-
