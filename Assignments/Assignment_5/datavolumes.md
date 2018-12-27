## Assignment: Database upgrades with named volumes
- Database upgrade with container
- Create a postgres container with named volume psql-data using version 9.6.1
- Use Docker Hub to learn VOLUME path and versions needed to run it
- Check logs, stop container
- Create a new postgres container with same named volume using 9.6.2
- Check a logs to validate


```
docker run --name some-postgres1 -e POSTGRES_PASSWORD=mysecretpassword -v postgresdata:/var/lib/postgresql/data -d postgres:9.6.1

docker ps

docker logs some-postgres1

docker volume ls

docker stop some-postgres1

docker run --name some-postgres2 -e POSTGRES_PASSWORD=mysecretpassword -v postgresdata:/var/lib/postgresql/data -d postgres:9.6.2

docker volume ls

docker logs  some-postgres2 S
```
