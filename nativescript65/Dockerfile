FROM wenhsiaoyi/ubuntu-base:node12
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>


# support multiarch: i386 architecture
# install essential tools
RUN dpkg --add-architecture i386 && \
    apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y --no-install-recommends g++ libncurses5:i386 libc6:i386 libstdc++6:i386 lib32gcc1 lib32ncurses5 lib32z1 zlib1g:i386

# Common environment variables
ENV DEBIAN_FRONTEND noninteractive
ENV _JAVA_OPTIONS -XX:+UnlockExperimentalVMOptions  -Xms512m -Xmx1G

# download and install Gradle
# https://services.gradle.org/distributions/
ARG GRADLE_VERSION=6.3
ARG GRADLE_DIST=bin
ENV GRADLE_HOME /opt/gradle

RUN cd /opt && \
    wget -q https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-${GRADLE_DIST}.zip && \
    unzip gradle*.zip && \
    ls -d */ | sed 's/\/*$//g' | xargs -I{} mv {} gradle && \
    rm gradle*.zip

# install android sdk
ENV ANDROID_HOME /opt/android-sdk
ARG ANDROID_SDK_VERSION=6200805

RUN mkdir -p ${ANDROID_HOME}/ && \
    wget -q https://dl.google.com/android/repository/commandlinetools-linux-${ANDROID_SDK_VERSION}_latest.zip && \
    unzip *tools*linux*.zip -d ${ANDROID_HOME}/ && \
    #rm *tools*linux*.zip && \
    export PATH="${PATH}:${GRADLE_HOME}bin/:${ANDROID_HOME}tools/:${ANDROID_HOME}tools/bin/:${ANDROID_HOME}platform-tools/:${ANDROID_HOME}/build-tools/:${ANDROID_HOME}/build-tools/bin" && \
    yes | ${ANDROID_HOME}/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME} --licenses && \
    ${ANDROID_HOME}/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME}  "tools"  "platform-tools" "platforms;android-29" "build-tools;29.0.3" "platforms;android-28" "build-tools;28.0.3" "extras;android;m2repository" "extras;google;m2repository"


RUN unzip -o *tools*linux*.zip -d ${ANDROID_HOME}/

# Using Debian, as root
RUN \
    npm install -g nativescript  --unsafe-perm \
        && apt-get clean \
        && rm -rf /var/cache/apk/* \
        && rm -rf /var/lib/apt/lists/* \
        && apt-get purge -y --auto-remove





# setup adb server
EXPOSE 5037

VOLUME ["/opt/projects"]
WORKDIR /opt/projects
#WORKDIR /opt/android-sdk

CMD ["/bin/bash"]
