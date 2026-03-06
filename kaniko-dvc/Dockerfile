FROM martizih/kaniko:v1.25.5-debug AS kaniko-src

FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
      python3.12 \
      python3.12-venv \
      python3-pip \
      git \
      bash \
      curl \
      ca-certificates \
    && python3.12 -m venv /opt/venv \
    && . /opt/venv/bin/activate \
    && pip install --no-cache-dir dvc dvc-gdrive \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="/opt/venv/bin:$PATH"
COPY --from=kaniko-src /kaniko /kaniko
COPY --from=kaniko-src /busybox /busybox
USER root
ENTRYPOINT [""]