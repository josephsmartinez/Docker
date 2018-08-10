Assignment: Manage Multiple Containers

    - Use docs.docker.com and --help
    - Run a nginx, mysql, httpd server
        Solution
            // Check the servers currently running
            $ docker container ls
            // Download the image and run the containers detached
            $ docker container run --publish 80:80 --detach --name [name the servers] [image to load name]
    - Run all of them --detach, name them with --name

    CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                               NAMES
    73f0878bb887        httpd               "httpd-foreground"       7 seconds ago       Up 6 seconds        80/tcp, 0.0.0.0:81->81/tcp   apache
    e07fadfe4113        mongo               "docker-entrypoint.s…"   22 hours ago        Up 22 hours         27017/tcp                    mango
    d0cb3e42cdee        nginx               "nginx -g 'daemon of…"   22 hours ago        Up 22 hours         0.0.0.0:80->80/tcp           fervent_hawking

    - nginx should listening on 80:80, httpd on 8080:80, mysql on 3306:3306

    // The containers where configured on the wrong port
    $ docker container stop [Container ID] [Container ID] [Container ID]
    // Lunch new containers with fixed port numbers
    S docker container run --publish 80:80 --detach --name nginx nginx
    $ docker container run --publish 8080:80 --detach --name apache httpd
    $ docker container run --publish 3306:3306 --detach --name mongo mongo
    $ docker container ls

    CONTAINER ID        IMAGE                COMMAND                  CREATED             STATUS              PORTS                               NAMES
    da85e3e7eee8        mongo               "docker-entrypoint.s…"   15 seconds ago      Up 14 seconds       0.0.0.0:3306->3306/tcp, 27017/tcp   mongo1
    857e90bad7cc        nginx               "nginx -g 'daemon of…"   4 minutes ago       Up 4 minutes        0.0.0.0:80->80/tcp                  nginx
    01d630e6c5e9        httpd               "httpd-foreground"       5 minutes ago       Up 5 minutes        0.0.0.0:8080->80/tcp                apache1

    - When running mysql, use the --env option (or -e) to pass in
      MY_SQL_RANDOM_ROOT_PASSWORD=yes

      // For this step assume the containers have been stopped
      $ docker container run -d -p 3307:3307 --name mysqldb1 -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql

    - Use docker container logs on mysql to find the random password it
      created on startup

      // Check the logs in the mysql container
      $ docker container logs mysqldb1

    - Clean up with docker container stop and docker container rm

        // Remove all the container in one shot
        $ docker rm $(docker ps -a -q)

    - Use docker container ls to ensure everything is correct before and
      after cleanup
