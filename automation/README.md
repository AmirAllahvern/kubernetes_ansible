Arvan Challenge
=========

Going to Create kubernetes cluster (Masters are HA) and install three node mariadb galera cluster to k8s cluster
then setup monitoring on kubernetes cluster.

How To Use
----------------

first put your hosts in `masters, workers and load balancer hosts group` in `inventory.ini` then just simply run the command below on an ansible-system
```bash
ansible-playbook -i inventory.ini main.yml
```