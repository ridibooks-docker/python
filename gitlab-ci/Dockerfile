FROM python:3.7-slim

ARG CONTAINER_ARCHITECTURE=linux-amd64
ARG AWS_CLI_VERSION=1.16.158
ARG ECS_CLI_VERSION=1.14.1
ARG DOCKER_COMPOSE_VERSION=1.23.2

ADD requirements.txt /tmp/requirements.txt

RUN apt-get update \
    && apt-get install -y \
        build-essential \
        curl \
        nodejs \
        npm \
    && pip3 install --upgrade \
        awscli==${AWS_CLI_VERSION} \
        docker-compose==${DOCKER_COMPOSE_VERSION} \
    && pip3 install -r /tmp/requirements.txt
    && curl -o /usr/local/bin/ecs-cli https://s3.amazonaws.com/amazon-ecs-cli/ecs-cli-${CONTAINER_ARCHITECTURE}-v${ECS_CLI_VERSION} \
    && chmod +x /usr/local/bin/ecs-cli \
    && rm -rf /var/lib/apt/lists/*

RUN npm install -g yarn webpack webpack-cli
