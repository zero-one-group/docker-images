FROM martizih/kaniko:v1.25.5-debug AS kaniko-src
FROM debian:bookworm-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
      python3 python3-pip python3-venv git bash \
    && python3 -m venv /opt/venv \
    && . /opt/venv/bin/activate \
    && pip install --no-cache-dir dvc dvc-gdrive \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="/opt/venv/bin:$PATH"
COPY --from=kaniko-src /kaniko /kaniko
COPY --from=kaniko-src /busybox /busybox
USER root
ENTRYPOINT [""]