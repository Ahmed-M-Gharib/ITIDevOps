What happens to data during container restart
When the container process crashes or restarts the data in emptyDir persists and is not lost because the emptyDir volume lifetime is tied to the Pod itself not the individual container

What happens to data when the pod is deleted
When the pod is deleted the emptyDir volume and all the data stored inside it are permanently deleted because emptyDir is ephemeral storage tied directly to the lifecycle of the Pod

Commands used
kubectl apply -f pod.yaml // 34an y aplly file el pod
kubectl exec -it scratch-lab -- sh -c echo hello > /data/msg.txt // 34an yektb hello gowwa el file
kubectl exec -it scratch-lab -- kill 1 // 34an yemawwet el container w yagarab el restart
kubectl exec -it scratch-lab -- cat /data/msg.txt // 34an yeqra el file w yet'akkad en el data lassa mawgouda
kubectl delete -f pod.yaml // 34an yemsa7 el pod bel kalmel
kubectl apply -f pod.yaml // 34an yekaret pod gded men el awal
kubectl exec -it scratch-lab -- cat /data/msg.txt // 34an yet'akkad en el data atmasa7et ba3d ma el pod atmasa7
