FROM wenhsiaoyi/ubuntu-base:node10
MAINTAINER Jack Wen <http://github.com/wenhsiaoyi>


# support multiarch: i386 architecture
# install essential tools
RUN dpkg --add-architecture i386 && \
    apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y --no-install-recommends g++ build-essential subversion nano usbutils iproute2 net-tools \
        iputils-ping libncurses5:i386 libc6:i386 libstdc++6:i386 lib32gcc1 lib32ncurses5 lib32z1 zlib1g:i386

# Common environment variables
ENV DEBIAN_FRONTEND noninteractive
ENV _JAVA_OPTIONS -XX:+UnlockExperimentalVMOptions  -Xms512m -Xmx1G

# download and install Gradle
# https://services.gradle.org/distributions/
ARG GRADLE_VERSION=6.3
ARG GRADLE_DIST=bin
ENV GRADLE_HOME /usr/local/gradle/

# install android sdk
ENV ANDROID_HOME /usr/local/android/sdk/
ENV ANDROID_SDK_HOME $ANDROID_HOME
ARG ANDROID_SDK_VERSION=6200805


COPY gradle-6.3-bin.zip /opt/
COPY commandlinetools-linux-${ANDROID_SDK_VERSION}_latest.zip /opt/

RUN cd /opt && \
    unzip gradle*.zip && \
    rm gradle*.zip && \
    ls -d */ | sed 's/\/*$//g' | xargs -I{} mv {} gradle && \
    mkdir -p ${ANDROID_HOME}/ && \
    unzip /opt/commandlinetools-linux-${ANDROID_SDK_VERSION}_latest.zip -d ${ANDROID_HOME}/ && \
    rm /opt/commandlinetools-linux-${ANDROID_SDK_VERSION}_latest.zip && \
    export PATH="${PATH}:${GRADLE_HOME}bin/:${ANDROID_HOME}tools/:${ANDROID_HOME}tools/bin/:${ANDROID_HOME}platform-tools/:${ANDROID_HOME}/build-tools/:${ANDROID_HOME}/build-tools/bin" && \
    #echo "24333f8a63b6825ea9c5514f83c2829b004d1feeroot@41ed651623a7" > "$ANDROID_HOME/licenses/android-sdk-license" && \
    yes | ${ANDROID_HOME}/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME} --licenses && \
    ${ANDROID_HOME}/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME}  "tools"  "platform-tools" "platforms;android-29" \
        "build-tools;29.0.3" "platforms;android-28" "build-tools;28.0.3" "extras;android;m2repository" \
        "extras;google;m2repository" && \
    echo 'export PATH="${PATH}:${GRADLE_HOME}bin/:${ANDROID_HOME}tools/:${ANDROID_HOME}tools/bin/:${ANDROID_HOME}platform-tools/:${ANDROID_HOME}/build-tools/:${ANDROID_HOME}/build-tools/bin"' >> /root/.bashrc



# setup adb server
#EXPOSE 5037
#EXPOSE 5554
#EXPOSE 5555
#EXPOSE 5900


CMD ["/bin/bash"]
