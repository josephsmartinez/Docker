# Simple applications with dependencies



## 12. Docker Port Mapping and Docker Log Commands


## 13. Docker Image Layers


## 14. Build Docker Images by Writing Dockerfile
```
docker build -t containerName/debain .
```

## 15. Build Docker Images by using Docker Commit Command
- Docker commint command saves the changes made to the Docker container file system to a new image.  
`docker commit container_ID repository_name:tag`  
Example:  
`docker commit [container_ID] [docker_account]/[os_version]:[tag]`  
**Avoid using latest tag by default**

## 16. Dockerfile in-depth
1. Chain RUN Instructions
- Each RUN command will execute the command on the top writable layer of the container, then commit the container as a new image.

2. Sort Multi-line Arguments Alphanumerically
- This will help you avoid duplication of packages and make the list much easier to update.
3. CDM Instructions
- CDM Instruction specifies what command you want to run when the container starts up.  
- if we don't specify CMD instruction in the Dockerfile, Docker will use the default command defined in the base image.
- exec command (preferred) vs shell command  

**Docker Cache**  
- Each time Docker executes an instruction it build a new image layer.
- The next time, if the instruction doesn't change, Docker will simply reuse the existing layer.

**This can cause issues when update need to run again**  
- Solution 1: Chain Instructions
- Solution 2:Specify `--no-cache` option  
`docker build -t [continer_name] . --no-cache=true`

### COPY
- Copies new files or directories from build context and adds them to the file system of the container.  
### ADD
- Copy and download a file from internet and copies to the container
- Automatically unpack compressed files  
**use COPY of the sake of transparency, unless absolutely sure ADD is needed**



## 17. Push Docker images to Docker Hub
`docker login`  
`docker push [repository_name]:[tag]`  

## 18. Containerize a Simple Application


## 19. Text Dirextion


## 20. Implement a Simple Key-value Lookup Service


## 21. Create Docker Container Links


## 22. Automate Current Workflow with Docker Compose


## 23. Deep Dive into Docker Compose Workflow


## 24. Kubernetes


[Dockerfile](https://docs.docker.com/get-started/part2/#define-a-container-with-dockerfile)  

Dockerfile defines what goes on in the environment inside your container. Access to resources like networking interfaces and disk drives is virtualized inside this environment, which is isolated from the rest of your system, so you need to map ports to the outside world, and be specific about what files you want to “copy in” to that environment. However, after doing that, you can expect that the build of your app defined in this Dockerfile behaves exactly the same wherever it runs.
