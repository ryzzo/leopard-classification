FROM python:3.10-slim

WORKDIR /workspace

RUN apt-get update && apt-get install -y --no-install-recommends \
    supervisor \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8888 6006