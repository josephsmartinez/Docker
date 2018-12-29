# Docker Compose Files

## Sections
- Docker Compose and The docker-compose.yml File
- Basic Commands Commands
- Assignment: Build a Compose File a Multi-Container Service
- Adding image building to compose files
- Assignment: Compose for run-time image building and Multi-Container Development

## Docker Compose Files
Example
```
version: '2'

# same as
# docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve

services:
  jekyll:
    image: bretfisher/jekyll-serve
    volumes:
      - .:/site
    ports:
      - '80:4000'
```
## Basic Commands Commands
See command.md with root directory.

## Assignment: Build a Compose File a Multi-Container Service
Please review assignment 6.

## Adding image building to compose files
- NOTE. Images are not rebuilt. You need to remove the image from the cache if you
want to re-build.

## Assignment: Compose for run-time image building and Multi-Container Development
Please review assignment 7.
