FROM wenhsiaoyi/ubuntu-base:androidsdk30
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>


# Common environment variables
ENV DEBIAN_FRONTEND noninteractive

# install essential tools
RUN \
    apt-get install -y g++ lib32z1 lib32ncurses5 libbz2-1.0:i386 libstdc++6:i386 && \
    npm install -g nativescript@6.8.0  --unsafe-perm \
        && apt-get clean \
        && apt-get purge -y --auto-remove





# setup adb server
EXPOSE 5037
EXPOSE 5554
EXPOSE 5555
EXPOSE 5900

#WORKDIR /opt/projects


CMD ["/bin/bash"]
