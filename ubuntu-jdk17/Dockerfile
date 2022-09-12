FROM wenhsiaoyi/ubuntu-base:jammy
LABEL com.hywen.jdk.image.authors="wenhsiaoyi@gmail.com"



#ENV PATH /usr/java/openjdk-17/bin:$PATH
#ENV JAVA_VERSION 11.0.7

# Common environment variables
ENV DEBIAN_FRONTEND noninteractive



RUN \
    apt-get -y upgrade \
    && add-apt-repository ppa:openjdk-r/ppa -y \
    && apt-get update \
    && apt-get install -y openjdk-17-jre \
    && apt-get install -y openjdk-17-jdk \
        && apt-get clean \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove


RUN export JAVA_HOME=/usr/java/openjdk-17 \
    && export PATH=$JAVA_HOME/bin:$PATH


CMD ["/bin/bash"]
