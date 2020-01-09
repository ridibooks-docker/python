FROM ubuntu:18.04

# Prepare
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y software-properties-common build-essential libssl-dev ca-certificates libmysqlclient-dev \
    && add-apt-repository --yes ppa:deadsnakes/ppa

# Install python3.7
RUN apt-get update \
    && apt-get install -y python3.7 python3-pip

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
