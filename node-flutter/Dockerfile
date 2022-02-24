FROM node:16-slim
LABEL maintainer="Doni Rubiagatra <doni@zero-one-group.com"


RUN apt-get update && apt-get install -y curl git unzip xz-utils zip libglu1-mesa wget

# Set up new user
RUN useradd -ms /bin/bash developer
USER developer
WORKDIR /home/developer

# Download Flutter SDK
RUN git clone https://github.com/flutter/flutter.git
ENV PATH "$PATH:/home/developer/flutter/bin"

# Run basic check to download Dart SDK
RUN flutter doctor

