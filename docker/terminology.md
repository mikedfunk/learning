# Docker Terminology

* [docker](https://docs.docker.com): Both a technology and a cli tool to manage docker, instances, swarms, run commands in containers, etc.
* [docker-toolbox](https://docs.docker.com/docker-for-mac/docker-toolbox/): Docker Toolbox installs docker, docker-compose and docker-machine in /usr/local/bin on your Mac.
* [docker-compose](https://docs.docker.com/compose/overview/): A tool for defining and running multi-container docker applications
* [docker-machine](https://docs.docker.com/machine/): An older tool that creates a docker environment in a virtualbox VM. Native is available for mac now, so it's not needed.
* [boot2docker](http://boot2docker.io/): The old way to install a lightweight linux version with docker and macosx (or others) on top of that. Or something. Now it's deprecated in favor of the native mac, etc. client.
* [docker labs](https://github.com/docker/labs): A cool tutorial to learn docker on github.

## Commands

`docker {cmd}`

* `run`: pull the related image from docker hub, create a new container for that image, run the default executable defined. e.g. `docker run hello-world`. You can also run different commands for containers e.g. `docker run alpine ls -l`
* `run -it {container} {cmd}`: run a command in interactive terminal.
* `pull`: pull the image from the docker registry to your local repository. e.g. `docker pull alpine`
* `images`: List all images you have downloaded
* `ps`: show active docker containers
* `ps -a`: like ps but including containers not running
* `stats`: memory usage for containers by container id

`docker-compose {cmd}`

* `up`: compose docker containers and provision them.
 * `--force-recreate`: otherwise will just pause and resume
 * `-d`: in the background. otherwise will be in foreground and show all logs from containers in output

`docker-machine {cmd}`

* `start`
* `stop`
* `restart`
* `status` whether it's running (text)
* `upgrade` get latest Boot2Docker on the vm
