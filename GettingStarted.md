# Command and other useful information to get started

Simple commands
```
docker version
docker info
docker --help
docker container run
docker run (old)
docker
```
Stop and remove all containers or images
```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker rmi $(docker images -q)
```
Images vs Containers

Images, application we want to run
Containers, an instance of that images running

Launches an NginX server
$ docker container run --publish 80:80 nginx
$ curl http://localhost

$ docker container ls
$ docker container stop [container i.d.]

// Detach the logs from shell window
// Traffic is -> port 80 host -> 80 container
$ docker container run --publish 80:80 --detach --name webhost nginx
$ docker container logs webhost

// Removing and force removing containers
$ docker container rm [ID] [ID] [ID]
$ docker container rm -f [ID] [ID] [ID]
$ docker container ls -a

Containers are "Restricted Processes" not a VM

$ docker run --name mongo -d mongo
$ docker top mongo
$ docker ps mongo
$ ps aux | grep mongo
$ docker stop mongo

Assignment: Manage Multiple Containers

- Use docs.docker.com and --help
- Run a nginx, mysql, httpd server
- Run all of them --detach, name them with --name
- nginx should listening on 80:80, httpd on 8080:80, mysql on 3306:3306
- When running mysql, use the --env option (or -e) to pass in
  MY_SQL_RANDOM_ROOT_PASSWORD=yes
- Use docker container logs on mysql to find the random password it
  created on startup
- Clean up with docker container stop and docker container rm
- Use docker container ls to ensure everything is correct before and
  after cleanup
