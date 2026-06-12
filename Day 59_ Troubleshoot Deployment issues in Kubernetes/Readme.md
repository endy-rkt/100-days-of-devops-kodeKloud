# Day 59: Troubleshoot Deployment issues in Kubernetes

**subject**

***

Last week, the Nautilus DevOps team deployed a redis app on Kubernetes cluster, which was working fine so far. This morning one of the team members was making some changes in this existing setup, but he made some mistakes and the app went down. We need to fix this as soon as possible. Please take a look.

The deployment name is`redis-deployment`. The pods are not in running state right now, so please look into the issue and fix the same.

`Note:`The`kubectl`utility on the`jump-host`has been configured to work with the Kubernetes cluster.

***

https://kubernetes.io/docs/reference/kubectl/generated/kubectl\_logs/

https://blog.stephane-robert.info/docs/conteneurs/orchestrateurs/outils/kubectl-get-describe-logs-top/

https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/

https://blog.stephane-robert.info/docs/conteneurs/orchestrateurs/kubernetes/configmaps/

https://blog.stephane-robert.info/docs/conteneurs/orchestrateurs/outils/kubectl-edit-patch-replace/

* Check the env

![](assets/z-wAHQ33Lw4_e0lh7xzMdJuZ029kbmedYC4CBN6ecPw=.png)

* Check logs and describe of the pod

![](assets/8hPTdYRos4ij9s2G5qAMMVSE3jAch_w5-tRtYBYrrm4=.png)

![](assets/qipcLzCOZlvJm9_pPMkhbQ__7A-bjStD8FkgWFXtq6o=.png)

![](assets/21xo2U2HcaR9lzw6Lvm5lh5xoouphnmr1N097aqZd5M=.png)

there qre like two errors:

* the docker image
* the volume for the configMap

- Check the configmap

![](assets/EpLpcZnRGDrl5BLRBdmb_sH0AmnVU7_cE0eWYgtHUqM=.png)

* Fix the deployment

before

![](assets/KdB77oT2seXkPk6WiIYdC6jPSsgoS8Q2eriOo_vl6Lg=.png)

![](assets/VfGPuxPFJxLlVRv3OQL61Q4gl_d2AUztmjTi4mKuweg=.png)

after

![](assets/Y7upzXyJgy3FxYmiOVaU2v-u7Af2Bt09Bubw1RCNRMg=.png)

* Check the result

![](assets/HtRBxn9RTQW164IlluZLRxiAyJ3aABm3K8GCeK9aIRY=.png)

