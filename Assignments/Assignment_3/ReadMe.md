# Assignment: DNS Round Robin Test

### Things to know
- How to use -it to get shell in a container
- Understand basic of what a Linux distribution is like Ubuntu and CentOS
- Know how to run a container
- Understand basic of DNS records

## DNS Round Robin Assignment
- Ever since Docker Engine 1.11, we can have multiple containers
  on a created network respond to the same DNS address.

- Create a new virtual network(default bridge driver)

- Create two containers from 'elasticsearch:2' image
- Research and use '--net-alias search' when creating them to
  give them an additional DNS name to respond to

- Run 'alpine nslookup search' with '--net' to see the two
  container list for the same DNS name

- Run 'centos curl -s search:9200' with '--net' multiple time    
  until you see both "name" field show.

## Process
- Create a new network
`docker network create my_new_network`
- Run new containers with the `--net-alias` flags
```
docker container run -d --network my_new_network --net-alias search elasticsearch:2
docker container run -d --network my_new_network --net-alias search elasticsearch:2
```
***NOTE: The container will be assigned new randoms name but the same alias.***
- Check the container are running and the configurations are correct
`docker container ps`
- We can a simple Alpine image with nslookup to check the new Containers
`docker container run --rm --network elastic_search alpine nslookup search`
- We can know run the `search` command from the centos images just lunched
`docker container run --rm --network elastic_search centos curl -s search:9200` 
