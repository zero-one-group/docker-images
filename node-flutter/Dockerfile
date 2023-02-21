FROM node:16-slim
LABEL maintainer="Doni Rubiagatra <doni@zero-one-group.com"

RUN apt-get update && apt-get install -y curl git unzip xz-utils zip libglu1-mesa wget musl musl-dev
RUN npm install -g pnpm

# Download Flutter SDK
RUN git clone -b 3.7.2 https://github.com/flutter/flutter.git --depth 1
ENV PATH "$PATH:/flutter/bin"

# Run basic check to download Dart SDK
RUN flutter doctor

