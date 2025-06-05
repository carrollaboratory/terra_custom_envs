FROM us.gcr.io/broad-dsp-gcr-public/terra-jupyter-python:1.1.6

USER root

# Install Python 3.12 and create venv
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python3.12 python3.12-venv python3.12-dev curl && \
    curl -sS https://bootstrap.pypa.io/get-pip.py | python3.12 && \
    python3.12 -m venv /opt/py312_venv && \
    /opt/py312_venv/bin/pip install --upgrade pip && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Leave Terra's Jupyter config alone
USER jupyter
