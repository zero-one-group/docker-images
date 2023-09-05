FROM --platform=linux/amd64 node:20-bookworm-slim
LABEL maintainer="Doni Rubiagatra <doni@zero-one-group.com"

RUN apt update && apt install -y python3-full python3-pip git
RUN npm install -g pnpm

RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"
