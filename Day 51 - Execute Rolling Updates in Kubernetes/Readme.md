# Day 51: Execute Rolling Updates in Kubernetes

**subjects**

***

An application currently running on the Kubernetes cluster employs the nginx web server. The Nautilus application development team has introduced some recent changes that need deployment. They've crafted an image`nginx:1.18`with the latest updates.

Execute a rolling update for this application, integrating the`nginx:1.18`image. The deployment is named`nginx-deployment`.

Ensure all pods are operational post-update.

`Note:`The`kubectl`utility on the`jump-host`has been configured to work with the Kubernetes cluster.

***

* Check the cluster

![](assets/Ods7m-krWcVvdyBNjKZw6vQN6fO5q74u1zgibkp4FZU=.png)

* Check replicaset

![](assets/o-wzcRLBbNP_9EH9F6Yp2DiwWcW_7mo_-Xw7z0zFIos=.png)

* Check the deployment

![](assets/z6bW56sjxavjG8iC7Tkm66AHso2SiaK_aziALu62PYA=.png)

![](assets/ZHTrf7fByIuK25r7qi_J4xV8MaU33UM9agGqdIs6ayo=.png)

* Update the deployment

![](assets/s8i5hwVeJ2_LLemPxscUnE7rTuH7QRyhuCkIveWaHHM=.png)

