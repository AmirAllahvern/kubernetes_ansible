Role
=========

Setup MariaDB Galera cluster 

This role uses helm to deploy MariaDB Galera cluster.

first create data directories in worker node, then apply pvs with filesystem volume.(In my case, my cluster didn't have any storage installed. if you have storage comment create and apply pvs.)

finally applies helm chart.

helm chart value file located in [files/values.yml](files/values.yml). 
use [Documentation](https://github.com/bitnami/charts/blob/master/bitnami/mariadb-galera) to change values.

* pay attention to [configure Quality of Service for pods](https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/). in production use cases QoS should be set `Busrstable class` or `Guaranteed class`.

Requirements
------------

At least should have one worker node.

kubernetes.core.k8s and kubernetes.core.helm modules are part of the kubernetes.core collection (version 2.3.1).

You might already have this collection installed if you are using the ansible package. It is not included in ansible-core. To check whether it is installed, run ansible-galaxy collection list.

To install it, use: ```ansible-galaxy collection install kubernetes.core```

Role Variables
--------------

- repo_name: helm repository name
- repo_url: helm repository url 
- kube_context: context name of destination cluster
- namespace: namespace name where you want to deploy helm chart
- release_name: helm install release name
- chart_name: name of chart want to deploy
- values_path: value file location in local

Author Information
------------------
e-mail: amir79allahvern@gmail.com

github: AmirAllahvern
