FROM ubuntu:16.04

RUN apt-get update 
RUN apt-get install -y vim build-essential
RUN apt-get install -y python3 python3-dev python3-pip
RUN apt autoremove -y \
    && rm -rf /var/lib/apt/lists/*

## Update pip
RUN pip3 install --upgrade pip wheel setuptools
