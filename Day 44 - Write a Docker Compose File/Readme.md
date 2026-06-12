# Day 44: Write a Docker Compose File

**subject**

***

The Nautilus application development team shared static website content that needs to be hosted on the `httpd` web server using a containerised platform. The team has shared details with the DevOps team, and we need to set up an environment according to those guidelines. Below are the details:



a. On `App Server 2` in `Stratos DC` create a container named `httpd` using a docker compose file `/opt/docker/docker-compose.yml` (please use the exact name for file).

b. Use `httpd` (preferably `latest` tag) image for container and make sure container is named as `httpd`; you can use any name for service.

c. Map `80` number port of container with port `6300` of docker host.

d. Map container's `/usr/local/apache2/htdocs` volume with `/opt/sysops` volume of docker host which is already there. (please do not modify any data within these locations).

***

* Write docker compose file

![](assets/sIWQ8yr5BK15rGr01z8hTOaZ_EOroazho52w4AcoqEs=.png)

* test

![](assets/dYs2y95auCTacn_ul0rln2tXrRDBKOu0j_C8IHoeW-g=.png)

![](assets/-KnMWgr_QT6ho5cUZC2MoSmLzrYCVxJqYO9VURIt1WI=.png)

