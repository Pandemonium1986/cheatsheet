<!-- markdownlint-disable MD001 MD013 MD025 MD036 -->

# Longhorn

## Tools versions

| Os / Tool | Version |
| :-------: | :-----: |
|   Sles    |  15sp6  |
|   Rke2    | 1.28.14 |
| Longhorn  |  1.7.2  |

## What is Longhorn?

Longhorn is a lightweight, reliable, and powerful distributed block storage system for Kubernetes.

Longhorn implements distributed block storage using containers and microservices. Longhorn creates a dedicated storage controller for each block device volume and synchronously replicates the volume across multiple replicas stored on multiple nodes. The storage controller and replicas are themselves orchestrated using Kubernetes.

With Longhorn, you can:

- Use Longhorn volumes as persistent storage for the distributed stateful applications in your Kubernetes cluster
- Partition your block storage into Longhorn volumes so that you can use Kubernetes volumes with or without a cloud provider
- Replicate block storage across multiple nodes and data centers to increase availability
- Store backup data in external storage such as NFS or AWS S3
- Create cross-cluster disaster recovery volumes so that data from a primary Kubernetes cluster can be quickly recovered from backup in a second Kubernetes cluster
- Schedule recurring snapshots of a volume, and schedule recurring backups to NFS or S3-compatible secondary storage
- Restore volumes from backup
- Upgrade Longhorn without disrupting persistent volumes

Longhorn comes with a standalone UI, and can be installed using Helm, kubectl, or the Rancher app catalog.
