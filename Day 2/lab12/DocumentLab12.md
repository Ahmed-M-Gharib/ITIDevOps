Static PV Binding Mechanics Lab

How PV capacity matching works
A PVC can only bind to a PV if the PV capacity is equal to or greater than the PVC requested size, so a 12Gi PVC stays Pending against a 10Gi PV

Why one PV cannot bind to multiple PVCs
PV and PVC binding is strictly a one-to-one relationship in Kubernetes, meaning once a PV binds to a PVC it is fully claimed and cannot be shared by another PVC even if unused capacity remains

Experiment Conclusions Table
| Question | Your conclusion |
|----------|-----------------|
| PV 10Gi + PVC 12Gi | PV remains Available and PVC stays Pending because PV capacity is smaller than requested PVC size |
| One PV 10Gi + two PVC 5Gi | Only one PVC becomes Bound (claim-a) while the second stays Pending (claim-b) due to 1-to-1 PV binding rule |

Commands used
kubectl apply -f exp_a.yaml // 34an y aplly exp A pv w pvc
kubectl get pv quiz-pv // 34an y3red status el pv
kubectl get pvc too-big // 34an y3red status el pvc
kubectl describe pvc too-big // 34an y3red events el pvc
kubectl delete pvc too-big // 34an ymss7 el pvc bss
kubectl apply -f exp_b.yaml // 34an y aplly exp B pvcs
kubectl get pvc // 34an y3red status el claim-a w claim-b
kubectl delete pvc claim-a claim-b // 34an ymss7 el pvcs
kubectl delete pv quiz-pv // 34an ymss7 el pv

