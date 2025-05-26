# 🌎 volumes-theory
Some of my notes as I learn about volumes in Kubernetes.

Docker also has a notion of volumes, but it is different from the Kubernetes's notion of volumes. They both do answer the same need but they are not the same.

Kubernetes has **2** types of volumes:
- Volumes
- PersistentVolume

These two are **not** the same, as PersistentVolume is a resource on its own whereas a volume is a pod configuration.

Volumes are *storage-bound to the Pod's lifecycle*. Volumes are nothing more than **storage attached to the life cycle of the Pod**. As soon as the pod is deleted, the volumes that were created with it are deleted too.

🚀 Run the script (emptyDir volume):

1) Create the pod:
```bash
kubectl apply -f emptydir.yml
```

2) Check if pods are running:
```bash
kubectl get pods
```

3) Exec into the container and see the volume:
```bash
kubectl exec pod/two-containers-with-empty-dir -c nginx-container -- ls /var
```

4) Or the other container:
```bash
kubectl exec pod/two-containers-with-empty-dir -c busybox-container -- ls /var
```

> ❗️ In the case of the hostPath volume, make sure you have the file created on your host before proceeding. Also keep in mind it is an antipattern.
