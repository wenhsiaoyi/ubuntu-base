# ubuntu-base with Open-JDK8

## build image
docker build -t wenhsiaoyi/ubuntu-base:jdk8 .
docker login
docker push wenhsiaoyi/ubuntu-base:jdk8

docker run --rm -it wenhsiaoyi/ubuntu-base:jdk8
