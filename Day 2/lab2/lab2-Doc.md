What happens to data during Pod deletion
The data persists even after deleting and recreating the Pod because hostPath mounts a directory directly from the underlying Node filesystem so the file remains stored on the host disk independently of the Pod lifecycle

Why hostPath is unsafe on a multi-node cluster
If the Pod is deleted and rescheduled onto a different Node on a multi-node cluster it will mount the local directory of that new Node which will not contain the data written on the previous Node

Commands used
kubectl apply -f pod.yaml // 34an y aplly file el pod
kubectl exec -it hostpath-lab -- sh -c echo node-disk > /data/note.txt // 34an yktb node-disk gowwa el file
kubectl delete -f pod.yaml // 34an yemsa7 el pod
kubectl apply -f pod.yaml // 34an yekaret el pod men gded
kubectl exec -it hostpath-lab -- cat /data/note.txt // 34an yet'akkad en el data lassa mawgouda ba3d el delete
