Role
=========

Create multi master and HA kubernetes cluster using kubeadm.

First install haproxy using apt package manager as masters load balancer and it handles control-plane-endpoint.
(* if you want to have fully high available control plane should have more than one load balancer, use [virtual ip address](https://en.wikipedia.org/wiki/Virtual_IP_address) to handle fault-tolerance)

At the lowest layers of a Kubernetes node is the software that, among other things, starts and stops containers. We call this the “Container Runtime”. The most widely known container runtime is Docker, but it is not alone in this space and now days containerd is being used.
so here I have used containerd as cri.

After installing load balancer and cri it's time to install kubeadm,kubelet,kubectl on cluster nodes.

And finally init kubeadm on master then join other masters and workers.
to join other master and worker , join command being produce in master which you run kubeadm init.
result should be applied in other nodes, so I save commands as scripts in files directory then And I will continue to use them.

Also, there are two handlers: one for restarting containerd systemd service and the other one for haproxy reload.

Requirements
------------

- community.general.modprobe module is part of the community.general collection
    You might already have this collection installed if you are using the ansible package. It is not included in ansible-core. To check whether it is installed, run ansible-galaxy collection list.
    
    To install it, use: ```ansible-galaxy collection install community.general```

Author Information
------------------
e-mail: amir79allahvern@gmail.com

github: AmirAllahvern