FROM python:3.7.3-slim

RUN apt-get update && apt-get install -y build-essential
RUN pip install --upgrade pip

ADD requirements.txt /opt/requirements.txt
RUN pip install -r /opt/requirements.txt --ignore-installed
