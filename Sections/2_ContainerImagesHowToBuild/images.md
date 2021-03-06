# Container Images, Where to find them and how to build them

- All about images, the building blocks of containers
- What's an image
- Using Docker Hub registry
- Building out own images

## The Mighty Hub: Using Docker Hub Registry Images

 What is an image  

- App binaries and dependencies
- Metadata about the image data and how to run the image
- Not a complete OS. No kernel, kernel modules (e.g. drivers)
- Small as one file (you app binary) like a golang static binary
- Big as a Ubuntu distro with apt, and Apache, PHP, and more installed

Docker Hub Registry  

- Basic of Docker Hub (hub.docker.com)
- Find official and other good public images
- Download images and basic of image tag

Images are not named, they are tagged. Am image can have more than one tag.  

A best practice when going into production is to:  
- Specify the exact version

## Images and Their Layers: Discover the Image Cache
- Image layers
- Union file system
- 'history' and 'inspect' command
- copy on write

Resources:
[images and container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)

Show layer of changes made in image  
`docker history [image name]`  

Every image starts with a blank layer known as "scratch"  

Then every set of change that happens after that on the file system, in the image, is another layer.  

JSON metadata about the image  
`docker images inspect [image name]`

## Image Tagging and Pushing to Docker Hub
- All about image tags
- How to upload to Docker Hub
- Image ID vs. Tag

Assign one or more tags to an image  
`docker image tag`

***Official Repositories***, they live at the "root namespace" of the registry, so they don't need account name in front of repo name.

***Tags*** are like git tags, not quite a branch and not quite a version.  

Change image tag
`docker image tag [ SOURCE IMAGE ] [ TARGET IMAGE ]`

***NOTE: if you don't specify the tag. It'll always default to latest.***

Upload changed layer to a image registry  
`docker image push [ image name ]`  

Logging into Docker to push images  
`docker login`  

Authentication Key  
`cat ..docker/config.json`  

***NOTE: docker login actually stores an authentication key that would allow local docker CLI to access Docker Hub.***

If using a un-trusted machine just logout    
`docker logout`

Quick Review
- Properly tagging images
= Tagging images for upload to Docker Hub
- How tagging is related to image ID
- The latest tag
- Logging into Docker Hub from docker cli

### Example using tags and pushing to dockerhub
```
docker login
docker pull nginx:example_name
docker image nginx voltair/nginx
docker push voltair/nginx
docker logout
```

## Building Images: The Dockerfile Basics
***Logging***, There's actually logging drivers that we can use in the Docker Engine itself to control all the logs.


## Building Images: Running Docker Builds
When building docker files keep the things the change the lest at the top of the file, while the things that change the most at the bottom.

`docker image build -t sample_nginx .`


## Building Images: Extending Official

## Assignment Build: Your Own Dockerfile and Run Container From it



## Assignment Answers: Build Your Own Dockerfile and Run Containers From it.
