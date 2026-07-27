Combined Stack Lab - ConfigMap, Secret, PVC and Sidecar

How ConfigMap subPath works without wiping destination directory
Using subPath allows mounting a specific key from a ConfigMap as a single file inside a container directory without replacing or hiding other existing files in that directory

Why PVC persists data across pod recreations
PersistentVolumeClaims decouple storage lifecycle from pod lifecycle allowing data written to the volume to remain intact on the underlying storage even when pods are deleted or restarted

Commands used
kubectl apply -f manifest.yaml // 34an y aplly all resources cm secret pvc w pod
kubectl get cm,secret,pvc,pod // 34an y3red el status bta3et el resources
kubectl exec notes-app -c web -- cat /usr/share/nginx/html/index.html // 34an ykteb content el welcome html
kubectl exec notes-app -c web -- ls /etc/notes-secret // 34an y3red el secret file gowwa web container
kubectl exec notes-app -c agent -- cat /data/heartbeat.log // 34an y3red el logs bta3et el heartbeat
kubectl delete pod notes-app // 34an ymss7 el pod w yjtbr el persistence bta3et el pvc

