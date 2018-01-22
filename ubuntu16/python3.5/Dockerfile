FROM ubuntu:16.04

## Install python3
RUN apt-get update 
RUN apt-get install -y vim build-essential
RUN apt-get install -y python3 python3-dev python3-pip

## Setting language
RUN apt-get install -y language-pack-ko

RUN locale-gen ko_KR.UTF-8
ENV LANG ko_KR.UTF-8
ENV LANGUAGE ko_KR.UTF-8
ENV LC_ALL ko_KR.UTF-8

## Setting timezion
ENV TZ Asia/Seoul

RUN echo $TZ > /etc/timezone
RUN apt-get install -y tzdata
RUN rm /etc/localtime
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata

## Clean up
RUN apt autoremove -y && rm -rf /var/lib/apt/lists/*

## Update pip
RUN pip3 install --upgrade pip wheel setuptools
