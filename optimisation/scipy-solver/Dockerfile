FROM python:3.8-slim

RUN apt-get update && apt-get install -y build-essential
RUN apt-get install -y libpq-dev postgresql-client
RUN pip install --upgrade pip

ADD requirements.txt /opt/requirements.txt
RUN pip install -r /opt/requirements.txt --ignore-installed
