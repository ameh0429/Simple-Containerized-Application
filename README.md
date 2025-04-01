# Containerized a Simple Application using Docker.

# Overview
I recently started learning docker and it was interesting. Docker uses client-server (docker-engine) architecture, it has its client components that talks to a server component using a restful API. A container is a special process running on your computer, all containers on a host share the operating system of the host.

# Prerequisites
- Docker CLI and Desktop Installed.
- Node.js v22.14.0
- Git

# Setup Instructions
- First, I wrote a simple application using node.js in `app.js` file

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mvxk6auqtt7vkwzo115e.png)
- I dockerized the application, meaning I made a small change so that it can be run by docker by adding a simple dockerfile. 

A dockerfile is a plain text file that includes instructions that docker uses to package up this application into an image.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9z5m2ospdi7ht4knapw3.png)

- To build the docker image, run the command

```
docker build -t hello-docker
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5oyx66hmjp60ffwhhahz.png)
- To run this image to on any computer running docker

```
docker run hello-docker
```
- Once we have the image; we can push it to DockerHub. DockerHub to docker is like GitHub to Git. It is a storage for docker images that anyone can use. The image must be tagged before pushing.

```
docker tag <image-id> <dockerhub-username>/<repository-name>:<tag>
```
- Then push

```
docker push amehmathias/hello-docker:latest
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/e5285n7lxsd6zd6m1t8w.png)

- Once our application image is on DockerHub, then we can put it on any machine running docker.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/p93qw68vaa3w8sk9ypls.png)

# Challenge faced
I encountered an error while trying to push my application image to DockerHub without first tagging it

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qw2ehol78gbgsqsapt6u.png)

Based on the error message on the terminal, I noticed I have to tag my image before pushing it.
