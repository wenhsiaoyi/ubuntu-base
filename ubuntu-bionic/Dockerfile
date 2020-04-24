FROM ubuntu:bionic
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>

# Common environment variables
ENV DEBIAN_FRONTEND noninteractive
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL en_US.UTF-8
ENV TZ 'Asia/Taipei'


# Install dependencies
CMD echo Install dependencies
RUN \
    export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin  \
        && export LANGUAGE="en_US.UTF-8"  \
        && export LANG="en_US.UTF-8"  \
        && export LC_ALL="en_US.UTF-8" \
        && apt-get update \
    && apt-get -y upgrade \
    && apt-get install -y apt-utils \
    && apt-get install --reinstall locales && dpkg-reconfigure locales \
    && locale-gen zh_TW zh_TW.UTF-8 zh_CN.UTF-8 en_US.UTF-8 \
    && apt-get install -y software-properties-common \
    && add-apt-repository universe \
    && apt install  -y language-pack-en-base language-pack-zh-hant  language-pack-zh-hant-base language-pack-zh-hans language-pack-zh-hans-base \
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
        && apt-get clean all \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove




# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

CMD echo Build finish

CMD ["/bin/bash"]
