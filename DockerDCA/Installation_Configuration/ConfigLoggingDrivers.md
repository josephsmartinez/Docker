# Configure Logging Drivers

## Get log file by using the HTTPD image using RSYSLOG

> docker images pull httpd rsyslog
> docker container run -d --name testweb httpd
> docker container inspect testweb | grep IPAddress
> yum install telnet elinks lynx curl
> curl 172.17.0.2
> docker log testweb
> vim /etc/syslog.conf

``` conf
# Provides UDP syslog reception
#$ModLoad imudp
#$UDPServerRun 514
$ModLoad imudp
$UDPServerRun 514
```

> systemctl start rsyslog
> vim /etc/docker/daemon.json

``` json
{
  "storage-driver":"devicemapper",
  "log-driver": "syslog",
  "log-opts": {
    "syslog-address": "udp://172.17.0.2:514"
  }
}
```

> systemctl restart docker
> curl http://127.0.0.1
> tail /var/log/messages

## Configure logging service on the CLI

> docker ccontainer run -d --name testjson --log-driver json-file httpd

Resources:

Configure logging drivers
https://docs.docker.com/config/containers/logging/configure/

Syslog logging driver
https://docs.docker.com/config/containers/logging/syslog/