ConfigMap as Volume Lab

What happens when mounting a ConfigMap over an existing directory
Mounting a ConfigMap volume over a container directory replaces and overwrites all existing files in that directory with the keys from the ConfigMap

Commands used
kubectl apply -f manifest.yaml // 34an y aplly file el configmap w el pod
kubectl exec -it nginx-site -- cat /usr/share/nginx/html/index.html // 34an ykteb el content w yet'aked en el file mawgoud
kubectl port-forward pod/nginx-site 8080:80 // 34an ya3mel forward le port 80 gowwa el pod
curl http://localhost:8080 // 34an yet'aked en el site shagal lesa b3d el port forward
