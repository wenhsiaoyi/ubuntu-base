FROM wenhsiaoyi/ubuntu-base:jdk17
LABEL com.hywen.node.image.authors="wenhsiaoyi@gmail.com"




# Common environment variables
ENV DEBIAN_FRONTEND noninteractive


# curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
# && curl -sL https://deb.nodesource.com/setup_12x | bash - \
# Using Debian, as root
RUN \
    apt-get update \
    && apt-get -y upgrade \
    && curl -sL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get install -y nodejs \
        && apt-get clean \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove


CMD ["/bin/bash"]
