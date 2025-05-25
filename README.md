# 🌎 volumes-theory
Some of my notes as I learn about volumes in Kubernetes.

Docker also has a notion of volumes, but it is different from the Kubernetes's notion of volumes. They both do answer the same need but they are not the same.

Kubernetes has **2** types of volumes:
- Volumes
- PersistentVolume

These two are **not** the same, as PersistentVolume is a resource on its own whereas a volume is a pod configuration.

Volumes are *storage-bound to the Pod's lifecycle*. Volumes are nothing more than **storage attached to the life cycle of the Pod**. As soon as the pod is deleted, the volumes that were created with it are deleted too.

