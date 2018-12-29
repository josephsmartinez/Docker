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
