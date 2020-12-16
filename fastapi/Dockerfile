FROM tiangolo/uvicorn-gunicorn:python3.8

RUN apt-get update && \
    apt-get install -y build-essential libcairo2 libpango-1.0-0 \
        libpangocairo-1.0-0 libgdk-pixbuf2.0-0 libffi-dev shared-mime-info

ADD requirements.txt /opt/requirements.txt
RUN pip install -r /opt/requirements.txt --ignore-installed
