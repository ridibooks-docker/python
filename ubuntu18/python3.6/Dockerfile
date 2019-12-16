FROM ubuntu:18.04

# Prepare
RUN apt-get update

# Install python3.6
RUN apt-get install -y python3.6 python3.6-dev python3-pip build-essential libssl-dev

# Setting timezion
ENV TZ Asia/Seoul
ENV DEBIAN_FRONTEND=noninteractive

RUN echo $TZ > /etc/timezone
RUN apt-get install -y tzdata
RUN rm /etc/localtime
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata

# Setting language
ENV LANG C.UTF-8
ENV LANGUAGE C.UTF-8
ENV LC_ALL C.UTF-8

# Setting python virtual env
RUN pip3 install --upgrade pip setuptools pipenv

# Clean up
RUN apt-get clean \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/*
