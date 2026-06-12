# Day 37: Copy File to Docker Container

**subject**

***

The Nautilus DevOps team possesses confidential data on`App Server 1`in the`Stratos Datacenter`. A container named`ubuntu_latest`is running on the same server.





Copy an encrypted file`/tmp/nautilus.txt.gpg`from the docker host to the`ubuntu_latest`container located at`/usr/src/`. Ensure the file is not modified during this operation.

***

https://docs.docker.com/reference/cli/docker/container/cp/

* Check the existing container

![](assets/4XqSUbjhuMR5-NWlu-abZF3InBMWsipED60K1WqGLZ0=.png)

* Copy file

![](assets/3HarXyRxPLzRUkJyhPl7QMDgWd-36O1NupCeRljplrc=.png)

* verify the gpg

![](assets/STxmD6csFAjYTOUlY8elHeOFp2Ah5cqqQDIirxzHSyE=.png)

