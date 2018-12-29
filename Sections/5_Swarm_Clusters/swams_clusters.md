# Swarm Intro and Crating a Three-node Swarm

## Sections
- Swam Mode - Built-in Orchestration
- Create a service and scale it locally
- UI Change for service create/update
- Docker Machine Bug on (VM)
- Creating a three-node cluster


## Swam Mode - Built-in Orchestration
docker swarm init: what is does
```
docker swarm init
```
### Losts of PKI and security automation
- root signing certificate created for our Swarm
- Certificate is issued for first manager node
- Join tokens are created
### Raft database created to store root CA, config and secrets
- encrypted by default on disk
- No need of another key/value system to hold orchestration/secrets
- Replicates logs amongst Managers via mutual TLS in "control plane"

## Create a service and scale it locally
Review commands within command.md file at the root directory.
```
docker service create alpine ping 8.8.8.8
docker service ps [images name]
docker service update [images name] --replicas 3
```
NOTE:
## UI Change for service create/update
Reference 61. Udemy

## Docker Machine Bug
- If you're planning to use docker-machine to create local VM's for Swarm, note there is a bug in 18.09.0 that prevents swarm network ports from listening. You'll need to hard-code a specific version of Docker for docker-machine to install as a workaround.

- More information is in this GitHub Issue, but try this to use a older version of docker until they patch docker-machine.

- In Mac/Linux or Windows with Bash/Zsh shell:
`export VIRTUALBOX_BOOT2DOCKER_URL=https://github.com/boot2docker/boot2docker/releases/download/v18.06.1-ce/boot2docker.iso`

- In Powershell:
`$env:VIRTUALBOX_BOOT2DOCKER_URL="https://github.com/boot2docker/boot2docker/releases/download/v18.06.1-ce/boot2docker.iso"`

- After setting the environment variable, then use docker-machine create and it'll use the old docker version.

## Creating a three-node cluster
