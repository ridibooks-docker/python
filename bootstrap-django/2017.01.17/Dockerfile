FROM ridibooks/python:ubuntu16-python3.6

RUN apt-get update && apt-get -y install \
        mysql-client \
        libmysqlclient-dev

RUN apt autoremove -y \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt

# Log file initialize
RUN mkdir /var/log/library
RUN touch /var/log/library/www.log

WORKDIR /htdocs/www
