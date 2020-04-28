FROM wenhsiaoyi/ubuntu-base:androidsdk
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>


# Common environment variables
ENV DEBIAN_FRONTEND noninteractive
#ENV _JAVA_OPTIONS -XX:+UnlockExperimentalVMOptions  -Xms512m -Xmx1G
#ENV GRADLE_HOME /opt/gradle
# install android sdk
#ENV ANDROID_HOME /opt/android-sdk/

# support multiarch: i386 architecture
# install essential tools
RUN \
    apt-get update -y && \
    apt-get upgrade -y && \
    npm install -g nativescript@5.4.2  --unsafe-perm \
        && apt-get clean \
        && apt-get purge -y --auto-remove





# setup adb server
EXPOSE 5037
EXPOSE 5554
EXPOSE 5555
EXPOSE 5900

#WORKDIR /opt/projects


CMD ["/bin/bash"]
