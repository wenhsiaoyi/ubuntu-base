# alpine with OpenJRE8

## build image
docker build -t wenhsiaoyi/ubuntu-base:alpine-jre8 .
docker login
docker push wenhsiaoyi/ubuntu-base:alpine-jre8

docker run --rm -it wenhsiaoyi/ubuntu-base:alpine-jre8


$ docker run -it --rm --name my-maven-project -v "$PWD":/usr/src/app -w /usr/src/app maven:3.2-jdk-8 mvn clean install


# Building local Docker image (optional)
https://hub.docker.com/_/maven
This is a base image that you can extend, so it has the bare minimum packages needed. If you add custom package(s) to the Dockerfile, then you can build your local Docker image like this:

$ docker build --tag my_local_maven:3.5.2-jdk-8 .
