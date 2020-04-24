FROM wenhsiaoyi/ubuntu-base:bionic
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>



ENV PATH /usr/java/openjdk-11/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV JAVA_VERSION 11.0.7
#ENV JAVA_URL=https://github.com/AdoptOpenJDK/openjdk11-binaries/releases/download/jdk-11.0.7%2B10/OpenJDK11U-jdk_x64_linux_hotspot_11.0.7_10.tar.gz

RUN locale-gen $LANG
# Common environment variables
ENV DEBIAN_FRONTEND noninteractive

RUN \
    timedatectl set-timezone Asia/Taipei \
    && add-apt-repository universe \
    && dd-apt-repository ppa:openjdk-r/ppa -y \
# Install dependencies
    && apt-get update \
        && apt-get install -y --no-install-recommends \
        gnupg2 software-properties-common \
        ca-certificates \
        netbase \
        apt-transport-https \
        xz-utils \
        subversion \
        openjdk-11-jre \
        openjdk-11-jdk \
        binutils \
        bzip2 \
        unzip \
        curl \
        wget && \

# Make info file about this build
    #printf "Build of nimmis/java:openjdk-11-jre-headless, date: %s\n"  `date -u +"%Y-%m-%dT%H:%M:%SZ"` && \



# Remove cache
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    apt-get purge -y --auto-remove

ENV JAVA_HOME /usr/java/openjdk-11
RUN export JAVA_HOME

CMD ["bash"]
