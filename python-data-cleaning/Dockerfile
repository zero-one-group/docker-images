FROM continuumio/miniconda3:4.9.2

RUN apt-get update && apt-get install -y build-essential

RUN conda install -c conda-forge mamba \
    && mamba install -c conda-forge \
        dvc dvc-s3 dvc-azure dvc-gdrive dvc-gs dvc-oss dvc-ssh

RUN pip install --upgrade pip
ADD requirements.txt /opt/requirements.txt
RUN pip install -r /opt/requirements.txt
