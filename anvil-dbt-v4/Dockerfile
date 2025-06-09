FROM us.gcr.io/broad-dsp-gcr-public/terra-jupyter-python:1.1.6

USER root
ENV PIP_USER= 

# Install Python 3.12 and create venv
RUN apt-get update && \
    apt-get install -y software-properties-common git && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python3.12 python3.12-venv python3.12-dev curl && \
    curl -sS https://bootstrap.pypa.io/get-pip.py | python3.12 && \
    python3.12 -m venv /opt/py312_venv && \
    /opt/py312_venv/bin/pip install --upgrade pip && \
    git clone https://github.com/NIH-NCPI/anvil_dbt_project.git /opt/anvil_dbt_project && \
    /opt/py312_venv/bin/pip install --no-cache-dir --no-user -r /opt/anvil_dbt_project/requirements.txt && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER jupyter
