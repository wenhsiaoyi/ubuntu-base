FROM wenhsiaoyi/ubuntu-base:bionic

MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>

ENV LANG en_US.UTF-8
RUN locale-gen $LANG
# Common environment variables
ENV DEBIAN_FRONTEND noninteractive

ENV JAVA_VERSION 1.8.0_252


# Install dependencies
RUN \
    apt-get -y upgrade && \
    add-apt-repository ppa:openjdk-r/ppa -y && \
    apt-get update && \
    apt-get install -y openjdk-8-jdk openjdk-8-jre

RUN \
    apt-get clean && \
    rm -rf /var/cache/apk/* && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get purge -y --auto-remove



# Sets language to UTF8 : this works in pretty much all cases
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN export JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64" && \
     echo 'export JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"' >> ~/.bashrc && \
     echo 'export PATH="${PATH}:${JAVA_HOME}/bin"' >> ~/.bashrc



CMD ["bash"]
