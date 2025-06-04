FROM us.gcr.io/broad-dsp-gcr-public/terra-jupyter-python:1.1.6


# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive \
    PYTHON_VERSION=3.12 \ 
    PIP_USER=true

USER root

# Install Python 3.12 and dependencies
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python${PYTHON_VERSION} python3.12-venv python3.12-dev curl && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 1 && \
    curl -sS https://bootstrap.pypa.io/get-pip.py | python3.12 && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install common Python packages
RUN python3 -m pip install --upgrade pip

# Set the working directory and user
ENV HOME=/home/jupyter
WORKDIR $HOME
USER jupyter