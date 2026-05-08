FROM node:22-slim
LABEL maintainer="Sintia <sintia@zero-one-group.com>"

RUN apt-get update && apt-get install -y \
    curl git unzip xz-utils zip \
    libglu1-mesa wget musl musl-dev \
    && rm -rf /var/lib/apt/lists/*

RUN npm install -g pnpm

RUN curl -fsSL https://moonrepo.dev/install/moon.sh -o /tmp/moon-install.sh && \
    bash /tmp/moon-install.sh 1.41.8 && \
    rm /tmp/moon-install.sh

ENV FLUTTER_VERSION=3.41.6
ENV PATH="/flutter/bin:/root/.moon/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN git clone -b ${FLUTTER_VERSION} https://github.com/flutter/flutter.git --depth 1 \
    && git config --global --add safe.directory /flutter \
    && flutter doctor \
    && rm -rf /flutter/bin/cache/artifacts/engine/linux* \
    && rm -rf /flutter/bin/cache/artifacts/engine/darwin* \
    && rm -rf /flutter/bin/cache/artifacts/engine/windows* \
    && rm -rf /flutter/bin/cache/artifacts/engine/web* \
    && rm -rf /flutter/examples \
    && rm -rf /flutter/dev \
    && rm -rf /root/.pub-cache