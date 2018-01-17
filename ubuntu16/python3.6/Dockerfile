FROM ubuntu:16.04

# Install python3.6
## Add python3.6 repository
RUN apt-get update
RUN apt-get install -y software-properties-common curl
RUN add-apt-repository ppa:jonathonf/python-3.6
RUN apt-get update

## Install Essential package
RUN apt-get install -y build-essential vim

## Install python3.6
RUN apt-get install -y python3.6 python3.6-dev

## Install pip3.6
RUN curl -o /tmp/get-pip.py "https://bootstrap.pypa.io/get-pip.py"
RUN python3.6 /tmp/get-pip.py

## Clean up
RUN apt-get remove -y software-properties-common curl \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/*
