# Selecting Storage Drivers

Check the storage mapping
> docker info | grep -i storage

Configuring Storage Drivers
/etc/docker/daemon.json
> vim /etc/docker/daemon.json

``` json
{
  "storage-driver":"devicemapper"
}
```

> ls -la /var/lib/docker/devicemapper

NOTE xfs filesystem is note supported unless kernel compile is done for support

Resources:

Configure and troubleshoot the Docker daemon
https://docs.docker.com/config/daemon/