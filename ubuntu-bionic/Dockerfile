FROM ubuntu:bionic
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>

# Common environment variables
ENV DEBIAN_FRONTEND noninteractive && \
 LANG 'en_US.UTF-8' && \
 LANGUAGE 'en_US:en' && \
 LC_ALL 'en_US.UTF-8' && \
 TZ 'Asia/Taipei' && \
 export LC_ALL=$LANG && \
 export LANG=$LANG && \
 echo $TZ > /etc/timezone && \
 export PATH=/usr/java/openjdk-11/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin


# Install dependencies
CMD echo Install dependencies
RUN apt-get update \
    && apt-get install -y software-properties-common apt-utils \
    && add-apt-repository universe \
    && apt-get update \
    && apt-get -y upgrade \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        netbase \
        apt-transport-https \
        xz-utils \
        subversion \
        locales \
        systemd \
        binutils \
        bzip2 \
        unzip \
        curl \
        wget \
        gnupg2 \
        && apt-get clean \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove


# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

CMD echo Build finish

CMD ["bash"]
