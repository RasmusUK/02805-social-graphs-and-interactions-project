FROM continuumio/miniconda3

RUN apt-get update && apt-get install -y \
    libgraphviz-dev \
    build-essential \
    && apt-get clean
    
WORKDIR /workspace

COPY environment.yml /workspace

RUN conda env create -f environment.yml

RUN echo "conda activate myenv" >> ~/.bashrc

SHELL ["conda", "run", "-n", "myenv", "/bin/bash", "-c"]
