FROM docker:latest

RUN apk update
RUN apk add python3 make mariadb-dev python3-dev gcc musl-dev
RUN rm -rf /var/cache/apk/*

RUN pip3 install --upgrade pip

ADD requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt
