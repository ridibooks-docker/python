FROM python:3.7.5-slim-buster

# Prepare
RUN apt-get update

# Install
RUN apt-get install -y build-essential libssl-dev default-mysql-client default-libmysqlclient-dev make

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

EXPOSE 8001
WORKDIR /htdocs/www

