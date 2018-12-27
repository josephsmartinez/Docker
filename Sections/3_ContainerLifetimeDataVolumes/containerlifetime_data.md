# Container Lifetime & Persistent Data: Volumes
### Section Overview
- Defining the problem of persistent data
- Key concepts with containers: immutable, ephemeral
- Learning and using Data Volumes
- Learning and using Bind Mounts
- Assignments

### Sections
- Persistent data: Data Volumes
- Persistent data: Binding Mounts
- Assignment: Database upgrades with named volumes
- Assignment: Database upgrades with named volumes
- Assignment: Edit code running in container with bind mounts

## Container Lifetime
- Container are usually immutable and ephemeral
- "immutable infrastructure": only re-deploy container, never change
- This is ideal scenario, but what about databases, or unique data?
- Docker gives us features to ensure these "separation of concerns"
- This is known as "persistent data"
- Two ways: Volumes and Bind Mounts
- Volumes: make special location outside of container UFS
- Bind Mounts: Link container path to host path

https://www.oreilly.com/ideas/an-introduction-to-immutable-infrastructure
https://12factor.net/
https://medium.com/@kelseyhightower/12-fractured-apps-1080c73d481c#.cjvkgw4b3
https://docs.docker.com/storage/

## Persistent data: Data Volumes
- volumes can be named

## Persistent data: Binding Mounts
- Maps a host file or directory to a container file or directory
- Basically just two locations pointing to same file(s)
- Again, skips UFS, and host files overwrite any in container
- Can't use in Dockerfile, must be at container run
```
run -v /User/john/Documents:/path/container (mac/linux)
run -v //c/User/john/Documents:/path/container (windows)
```
## Assignment: Database upgrades with named volumes
- Database upgrade with container
- Create a postgres container with named volume psql-data using version 9.6.1
- Use Docker Hub to learn VOLUME path and versions needed to run it
- Check logs, stop container
- Create a new postgres container with same named volume using 9.6.2
- Check a logs to validate

## Assignment: Bind Mounts
- Use a Jekyll "Static Site Generator" to start a local web server
- Don't have to web developer: this is example of binding the gap between local file access and apps running in containers.
- Source code is in the course repo under bindmount-sample-1
- We edit file with editor on our host using native tools
- Container detect changes with host files and updates web server
- start container with `docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve`
- Refresh our browser to see the changes
- Change the file in `_post/` and refresh browser to see changes
