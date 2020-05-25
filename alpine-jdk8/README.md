## build image
docker build -t wenhsiaoyi/ubuntu-base:alpine-jdk8 --cache-from wenhsiaoyi/ubuntu-base:alpine-jdk8 .
docker login
docker push wenhsiaoyi/ubuntu-base:alpine-jdk8






alpine:3.11.6



