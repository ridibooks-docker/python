FROM ridibooks/account-python:ubuntu18-python3.6

RUN apt-get update && apt-get -y install \
        mysql-client \
        libmysqlclient-dev

RUN apt autoremove -y \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install --upgrade pip

COPY requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt

WORKDIR /htdocs/www
