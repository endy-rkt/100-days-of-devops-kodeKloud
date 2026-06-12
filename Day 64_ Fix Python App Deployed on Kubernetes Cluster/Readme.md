# Day 64: Fix Python App Deployed on Kubernetes Cluster

**subject**

***

One of the DevOps engineers was trying to deploy a python app on Kubernetes cluster. Unfortunately, due to some mis-configuration, the application is not coming up. Please take a look into it and fix the issues. Application should be accessible on the specified nodePort.

1. The deployment name is `python-deployment-xfusion`, its using `poroko/flask-demo-app` image. The deployment and service of this app is already deployed.
2. nodePort should be `32345` and targetPort should be python flask app's default port.

`Note:` The `kubectl` utility on the `jump-host` has been configured to work with the Kubernetes cluster.

***

* Check the env

![](assets/hn57le8Bb0jUhTCHbJHOfVU1U0WwLmP945rBAFOTQ1o=.png)

the pod and deploy has error

* Check logs

![](assets/M9hiRN1Ie7ccW7FqPdbZnwt0agBumo3NsZL3v5lEUEY=.png)

* Check the deployment manifest

![](assets/mCd_fprjIAsGUrwlCLbmfS3OErdQlXpq10v772hvk8k=.png)

![](assets/xnYwwH9APp0RoTdmoe8hwS37ViWQdw99KTSF85ZjPH8=.png)

* Fix the deployment

![](assets/OKISGAEeJcoOmW4Ba1yNTujEVS_F_6Iw4kajxhdBYRI=.png)

![](assets/XrVJCQC5SdjF-M2uOgrieDnZQ0DZ_IZtyY7BIX2jFps=.png)

* Check the service that the app is using

![](assets/n14PIDE3HgeGk6XTR0BkXMBCkj7BDgIsObuFZ5FlQ9o=.png)

we know the label used then

![](assets/ZMTIlNXlcyV7PZgfXJv-qWkYlwGp9pK3gBXGCeSMmyw=.png)

![](assets/YnyqGQ5l0GnlA0qrVsNHSHaTbJx_rQYCwFYPrRdVlyQ=.png)

![](assets/IdF_UOoJoYfThGQDOCKjpjhJ9N3iFf4zoP4YsFDT8pk=.png)

* fix the svc port

![](assets/2YQI8xLXAG7GeFk1-SAy01Xl3gESLY32pADb1_GAiB0=.png)

![](assets/OTOYDLyehsVRB-7Tz07UXH8tR6zz1u82qd4m_R0z17A=.png)

![](assets/Y0MkkT7SE38A1JlHhR7atCBa19aqsdlORi3C432kBfI=.png)

* Check the result

![](assets/s8SwF5h-oj3_kgcgqUqhr9kBzoXJXaaPiM3spUGQK-w=.png)

![](assets/vQENPlW3VChwnbVsNcwMFQhtayc8iaSBpVoufBIixSU=.png)
