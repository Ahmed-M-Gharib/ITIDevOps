Sidecar with shared volume Lab

How shared emptyDir volumes enable communication between containers
Shared emptyDir volumes provide a common file system space accessible by all containers in the same Pod allowing one container to write data and another to read or process it in real time

Why container flag -c is required for multi-container pods
Specifying -c is mandatory for multi-container pods because kubernetes cannot determine which container logs to output when multiple containers run in the same pod

Commands used
kubectl apply -f manifest.yaml // 34an y aplly file el pod
kubectl logs pair-lab -c reader -f // 34an y3red el logs bshkl continuous mn el reader container
kubectl logs pair-lab // 34an ywerry el error eno lazm y7dd el container name
