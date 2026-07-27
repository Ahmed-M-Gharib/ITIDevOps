ConfigMap from file as Volume Lab

How --from-file flag creates configmap keys from local files
Using the --from-file flag automatically maps the filename as the ConfigMap key and its file content as the key value allowing easy management of existing configuration files without manual YAML embedding

Why mounting configmap as readOnly is important
Mounting ConfigMaps as readOnly prevents runtime processes inside the container from altering configuration files which maintains consistency and security

Commands used
echo "server_tokens off;" > nginx-extra.conf // 34an ycreaty el nginx-extra.conf file
echo "FROM-FILE-LAB" > banner.txt // 34an ycreaty el banner.txt file
kubectl create configmap files-cm --from-file=nginx-extra.conf --from-file=banner.txt // 34an ycreaty el configmap mn el files
kubectl get cm files-cm -o yaml // 34an y3red el cm content w el keys
kubectl apply -f pod.yaml // 34an y aplly el pod
kubectl exec -it files-pod -- ls -la /etc/files // 34an y3red el files gowwa /etc/files
kubectl exec -it files-pod -- cat /etc/files/banner.txt // 34an y3red content el banner file

