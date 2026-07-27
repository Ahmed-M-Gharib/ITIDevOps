PVC Resize Lab

How allowVolumeExpansion enables storage resizing in kubernetes
Setting allowVolumeExpansion to true in a StorageClass permits patching a PVC to request a larger storage size dynamically without recreating the volume

Observed cluster behavior on local-path provisioner
On K3s local-path provisioner the PVC patch successfully updates the spec request to 2Gi but the capacity remains 1Gi or shows ExternalExpanding condition because dynamic filesystem expansion is not natively supported by local-path drivers unlike cloud CSI provisioners

Commands used
kubectl apply -f manifest.yaml // 34an y aplly el sc, pvc w el pod
kubectl patch pvc resize-lab-pvc -p '{"spec":{"resources":{"requests":{"storage":"2Gi"}}}}' // 34an y3ml resize lel pvc l 2Gi
kubectl get pvc resize-lab-pvc // 34an y3red el pvc status w el capacity
kubectl describe pvc resize-lab-pvc // 34an y3red el events bta3et el expansion
kubectl exec -it resize-lab -- df -h /data // 34an y3red el filesystem size gowwa el container

