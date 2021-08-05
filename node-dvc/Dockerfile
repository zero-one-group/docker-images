FROM node:16.3-slim

RUN apt-get update && apt-get install -y build-essential wget

RUN wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh \
    && bash ~/miniconda.sh -b -p /opt/anaconda \
    && rm ~/miniconda.sh

ENV PATH="/opt/anaconda/bin:$PATH" 

RUN conda install -c conda-forge mamba \
    && mamba install -c conda-forge \
        dvc dvc-s3 dvc-azure dvc-gdrive dvc-gs dvc-oss dvc-ssh

RUN apt-get update && apt-get install -y libglu1 libxi6 libgconf-2-4
