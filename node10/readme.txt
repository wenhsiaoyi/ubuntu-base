# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:node10 .
docker login
docker push wenhsiaoyi/ubuntu-base:node10



docker run --rm -it wenhsiaoyi/ubuntu-base:node10

