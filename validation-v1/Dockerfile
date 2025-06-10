FROM us.gcr.io/broad-dsp-gcr-public/terra-jupyter-python:1.1.6

USER root
ENV PIP_USER= 

# Install Python 3.9 and create venv
RUN apt-get update && \
    apt-get install -y software-properties-common git && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python3.9 python3.9-venv python3.9-dev curl && \
    curl -sS https://bootstrap.pypa.io/get-pip.py | python3.9 && \
    python3.9 -m venv /opt/py39_venv && \
    /opt/py39_venv/bin/pip install --upgrade pip && \
    git clone https://github.com/carrollaboratory/ftd-omop-validator.git /opt/ftd-omop-validator && \
    /opt/py39_venv/bin/pip install --no-cache-dir --no-user -r /opt/ftd-omop-validator/requirements.txt && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER jupyter