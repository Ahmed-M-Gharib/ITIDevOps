Custom StorageClass as Default Lab

How changing default storageClass works in kubernetes
Setting a StorageClass as default relies on the storageclass.kubernetes.io/is-default-class annotation, and only one StorageClass must be marked as default at any time to avoid provisioning conflicts

Why restoring default StorageClass is critical
Restoring the original default StorageClass prevents breaking subsequent deployment workloads in shared or training clusters that rely on the standard default provisioner

Commands used
kubectl apply -f manifest.yaml // 34an y aplly el custom sc, pvc w el pod
kubectl annotate sc local-path storageclass.kubernetes.io/is-default-class- // 34an y4el el default mn local-path
kubectl annotate sc student-local storageclass.kubernetes.io/is-default-class=true // 34an y5ly student-local hwa el default
kubectl get sc // 34an y3red el storage classes w yet'aked mn el default status
kubectl get pvc sc-lab-pvc // 34an y3red el pvc status w enha bound
kubectl delete pod sc-lab // 34an ymss7 el pod
kubectl delete pvc sc-lab-pvc // 34an ymss7 el pvc
kubectl annotate sc student-local storageclass.kubernetes.io/is-default-class- // 34an y4el el default mn student-local
kubectl annotate sc local-path storageclass.kubernetes.io/is-default-class=true // 34an yrgg3 local-path default tane

