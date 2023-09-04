FROM --platform=linux/amd64 node:20-alpine
LABEL maintainer="Doni Rubiagatra <doni@zero-one-group.com"

RUN apk add --no-cache git
RUN npm install -g pnpm

# Install python
RUN apk add --update --no-cache python3
RUN ln -sf python3 /usr/bin/python
RUN python3 -m ensurepip
RUN pip3 install --no-cache --upgrade pip setuptools
