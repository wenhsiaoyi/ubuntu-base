FROM wenhsiaoyi/ubuntu-base:jdk8
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>




# Common environment variables
ENV DEBIAN_FRONTEND noninteractive



# Using Debian, as root
RUN \
    apt-get update \
    && apt-get -y upgrade \
    && curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get install -y nodejs \
        && apt-get clean \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove


CMD ["/bin/bash"]
