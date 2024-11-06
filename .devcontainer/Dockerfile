# Use the Miniconda3 image as the base
FROM continuumio/miniconda3

# Update apt-get and install libgraphviz-dev
RUN apt-get update && apt-get install -y \
    libgraphviz-dev \
    build-essential \
    && apt-get clean
    
# Set the working directory in the container
WORKDIR /workspace

# Copy the environment.yml to the container
COPY environment.yml /workspace

# Create the conda environment from environment.yml
RUN conda env create -f environment.yml

# Activate the environment by default in the container
RUN echo "conda activate myenv" >> ~/.bashrc

# Make sure the environment is activated when running commands in the container
SHELL ["conda", "run", "-n", "myenv", "/bin/bash", "-c"]
