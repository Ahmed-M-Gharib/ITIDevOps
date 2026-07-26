Secret as Volume Lab

How secrets are exposed when mounted as a volume
Mounting a secret as a volume creates individual files for each secret key inside the mounted directory holding their respective values

Why mounting as readOnly is important
Mounting secrets as readOnly prevents processes inside the container from modifying or tampering with sensitive security credentials

Commands used
kubectl apply -f manifest.yaml // 34an y aplly file el secret w el pod
kubectl exec -it secret-files -- ls -la /etc/api // 34an y3red el files gowwa el directory
kubectl exec -it secret-files -- cat /etc/api/token // 34an ykteb el content w yet'aked en el token s7
kubectl exec -it secret-files -- cat /etc/api/user // 34an ykteb el content w yet'aked en el user s7
