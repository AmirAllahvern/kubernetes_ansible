Role Name
=========

Prepare virtual machines.

Apt package manager is forbidden in my country, so I wrote tasks to configure proxy for apt.

The Kubernetes scheduler determines the best available node on which to deploy newly created pods. If memory swapping is allowed to occur on a host system, this can lead to performance and stability issues within Kubernetes. For this reason, Kubernetes requires that you disable swap in the host system.

If you have multiple disks use mount_disk tasks to make file system and mount the second disk.


Role Variables
--------------

- disk: second disk path want to mount as sdb
- destination: directory path want to mount second disk
- filesystem: second disk format
- proxy: proxy url to configure for apt package manager


Author Information
------------------
e-mail: amir79allahvern@gmail.com

github: AmirAllahvern
