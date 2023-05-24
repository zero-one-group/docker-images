FROM ubuntu:22.04

# Prerequisites
RUN apt update && apt install -y curl git unzip xz-utils zip libglu1-mesa openjdk-11-jdk wget build-essential pkg-config ruby-full

# Install bundler fastlane 
RUN gem install bundler fastlane
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
 
WORKDIR /home/ubuntu

# Prepare Android directories and system variables
RUN mkdir -p Android/sdk/cmdline-tools/
ENV ANDROID_SDK_ROOT /home/ubuntu/Android/sdk
RUN mkdir -p .android && touch .android/repositories.cfg

# Set up Android SDK
RUN wget -O sdk-tools.zip https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip && \
 unzip sdk-tools.zip && rm sdk-tools.zip && \
 mv cmdline-tools Android/sdk/cmdline-tools/latest && \
 cd Android/sdk/cmdline-tools/latest/bin && \
 yes | ./sdkmanager --licenses && \
 ./sdkmanager "cmdline-tools;latest" "build-tools;29.0.2" "patcher;v4" "platform-tools" "platforms;android-32" "sources;android-32"
ENV PATH "$PATH:/home/ubuntu/Android/sdk/platform-tools"

# Download Flutter SDK
ARG FLUTTER_VERSION
RUN git clone -b $FLUTTER_VERSION https://github.com/flutter/flutter.git --depth 1
ENV PATH "$PATH:/home/ubuntu/flutter/bin" 

# Run basic check to download Dark SDK
RUN flutter doctor 