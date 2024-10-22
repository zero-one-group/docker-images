# Stage 1: Base image to install all build dependencies
FROM node:lts-slim AS build

ENV GO_VERSION=1.23.2

RUN apt-get update && apt-get install -y curl git unzip xz-utils zip libglu1-mesa wget musl musl-dev bash

# Install pnpm globally
RUN npm install -g pnpm

# Install Golang
RUN wget https://golang.org/dl/go$GO_VERSION.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go$GO_VERSION.linux-amd64.tar.gz

RUN curl -fsSL https://moonrepo.dev/install/moon.sh | bash

# Stage 2: Final image with minimal runtime dependencies
FROM node:lts-slim

LABEL maintainer="Mhd Ramadhan Arvin <madhan@zero-one-group.com>"

RUN apt-get update && apt-get install -y curl git unzip xz-utils zip libglu1-mesa wget musl musl-dev postgresql-client

# Copy Golang from the build stage
COPY --from=build /usr/local/go /usr/local/go

COPY --from=build /root/.moon/bin /root/.moon/bin
ENV PATH="/root/.moon/bin:$PATH"

# Install pnpm globally
RUN npm install -g pnpm

# Set PATH for Go and Flutter
ENV PATH="$PATH:/usr/local/go/bin"
