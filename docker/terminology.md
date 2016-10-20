# Docker Terminology

* [docker](https://docs.docker.com): Both a technology and a cli tool to manage docker, instances, swarms, run commands in containers, etc.
* [docker-toolbox](https://docs.docker.com/docker-for-mac/docker-toolbox/): Docker Toolbox installs docker, docker-compose and docker-machine in /usr/local/bin on your Mac.
* [docker-compose](https://docs.docker.com/compose/overview/): A tool for defining and running multi-container docker applications
* [docker-machine](https://docs.docker.com/machine/): An older tool that creates a docker environment in a virtualbox VM. Native is available for mac now, so it's not needed.
* [boot2docker](http://boot2docker.io/): The old way to install a lightweight linux version with docker and macosx (or others) on top of that. Or something. Now it's deprecated in favor of the native mac, etc. client.

## Commands

`docker {cmd}`

* **run** pull the related image from docker hub, create a new container for that image, run the executable defined. e.g. `docker run hello-world`
* **pull** pull the image from the docker registry to your local repository. e.g. `docker pull alpine`
