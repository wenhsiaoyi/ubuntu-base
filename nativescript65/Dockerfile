FROM wenhsiaoyi/ubuntu-base:androidsdk
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>


# Common environment variables
ENV DEBIAN_FRONTEND noninteractive

# install essential tools
RUN \
    apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y build-essential \
        g++ lib32z1 lib32ncurses5 libbz2-1.0:i386 libstdc++6:i386 && \
    npm install -g nativescript@6.5.0  --unsafe-perm \
        && apt-get clean \
        && apt-get purge -y --auto-remove





# setup adb server
EXPOSE 5037
EXPOSE 5554
EXPOSE 5555
EXPOSE 5900

#WORKDIR /opt/projects


CMD ["/bin/bash"]
