PVC Lab

Why data survives Pod deletion with PVC
Data survives Pod deletion because the persistent volume exists independently of the Pod lifecycle allowing a new Pod to reconnect to the exact same persistent storage

Default StorageClass name
The default StorageClass name in k3s is local-path

Commands used
kubectl apply -f manifest.yaml // 34an y aplly file el pvc w el pod
kubectl get pvc,pv // 34an y3red el pvc w el pv w yet'aked en el status Bound
kubectl exec -it pvc-lab -- sh -c echo survived > /data/state.txt // 34an ykteb survived gowwa el file
kubectl delete pod pvc-lab // 34an yemsa7 el pod bas w yseeb el pvc
kubectl apply -f manifest.yaml // 34an yekaret el pod men gded
kubectl exec -it pvc-lab -- cat /data/state.txt // 34an ykteb el content w yet'aked en el data lesa mawgouda b3d el delete
