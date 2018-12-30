# Commands

```
docker compose --help
docker compose logs
docker compose up
docker compose down


docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker rmi $(docker images -q)

docker swarm --help
docker swarm init

docker node --help
docker node ls

docker service --help
docker service create alpine ping 8.8.8.8
docker service ps [images name]
docker service update [images name] --replicas 3
```

### Example for swarms
- Add nodes to swarm and configure managers and workers.
```
docker swarm init
docker node ls
docker node update --role [manager or worker] [node name]
```
Get the key/tokenß
```
docker swarm join-token manager
```
