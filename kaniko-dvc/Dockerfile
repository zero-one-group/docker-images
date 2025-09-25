FROM martizih/kaniko:v1.25.0-debug AS kaniko-src

FROM alpine:3.20

# Install runtime + build deps
RUN apk add --no-cache \
      python3 py3-pip git bash \
      gcc musl-dev python3-dev linux-headers \
 && python3 -m venv /opt/venv \
 && . /opt/venv/bin/activate \
 && pip install --no-cache-dir dvc dvc-gdrive \
 # optional: upgrade pip supaya lebih stabil
 && pip install --no-cache-dir --upgrade pip \
 # cleanup build deps
 && apk del gcc musl-dev python3-dev linux-headers

ENV PATH="/opt/venv/bin:$PATH"

COPY --from=kaniko-src /kaniko /kaniko
COPY --from=kaniko-src /busybox /busybox

USER root
ENTRYPOINT [""]