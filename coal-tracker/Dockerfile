FROM python:3.9

RUN apt-get update && apt-get install -y build-essential
RUN pip install --upgrade pip

ADD requirements.txt /opt/requirements.txt
RUN pip install -r /opt/requirements.txt --ignore-installed
