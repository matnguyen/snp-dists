FROM ubuntu:latest

USER root
WORKDIR /

# Install requirements
RUN apt-get update && \
    apt-get install -y \
    git \
    build-essential \
    libz-dev && \
    rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/matnguyen/snp-dists.git && \
    cd /snp-dists && \
    make && \
    chmod +x /snp-dists/snp-dists

WORKDIR /data

ENV PATH="${PATH}:/snp-dists"
