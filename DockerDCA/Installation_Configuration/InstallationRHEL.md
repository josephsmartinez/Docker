# Docker Installation CentOS

> sudo yum install -y yum-utils device-mapper-persistent-data lvm2
> sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
> yum update -y
> sudo yum install docker-ce docker-ce-cli containerd.io
> sudo systemctl start docker && sudo systemctl enable docker && systemctl status docker

Get Dockerd Setting and Information

> docker info
