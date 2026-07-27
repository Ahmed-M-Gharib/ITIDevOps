Static PV and PVC Lab

How static persistent volume binding works
Static provisioning requires pre-allocating a PersistentVolume manually and using empty storageClassName with volumeName inside the PVC to bind directly to that specific PV without triggering dynamic provisioners

Why retain policy keeps data intact when PVC is deleted
The Retain policy ensures that when a PVC is deleted the underlying PV is not automatically wiped or destroyed allowing administrators to recover or reclaim data manually

Commands used
kubectl apply -f manifest.yaml // 34an y aplly el pv el pvc w el pod
kubectl get pv lab-static-pv // 34an y3red el status bta3et el pv w eno bound
kubectl get pvc lab-static-pvc // 34an y3red el status bta3et el pvc
kubectl exec -it lab-static -- cat /data/proof.txt // 34an y3red content el proof file
kubectl delete pod lab-static // 34an ymss7 el pod el awal
kubectl delete pvc lab-static-pvc // 34an ymss7 el pvc w yet'aked mn el released status

