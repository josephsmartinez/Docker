# Swarm Configuration

## Topic

- Configure Primary Manager Node
- Back up and restores

## Configure Primary Manager

> ifconfig
> docker swarm init --advertise-addr 10.136.199.130

``` text
 docker swarm join --token SWMTKN-1-3oi5bzy9n461ojjgm9ulq66dcw2tmdwwsknjinv36t1tqnvhc8-18s2eo815gv0ekqbmcji3t6ml 10.136.199.130:2377
```

> docker node ls
> docker system info

Worker node token
> docker swarm join-token worker

Manager tokens
> docker swarm join-token manager

## Joining worker nodes to the swarm

Create the join token
> docker swarm join-token worker

open the firewall to allow connecting nodes
> firewall-cmd --permanent --add-port=2377/tcp
> firewall-cmd --reload

Check joined nodes
> docker system info
> docker node ls

## Backup and Restore
