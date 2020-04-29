FROM python:3.7-slim

ARG CONTAINER_ARCHITECTURE=linux-amd64
ARG AWS_CLI_VERSION=1.18.47
ARG ECS_CLI_VERSION=1.17
ARG DOCKER_COMPOSE_VERSION=1.25.2

RUN apt-get update \
    && apt-get install -y \
        build-essential \
        curl \
        docker.io \
    && pip3 install --upgrade \
        awscli==${AWS_CLI_VERSION} \
        docker-compose==${DOCKER_COMPOSE_VERSION} \
    && curl -o /usr/local/bin/ecs-cli https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-${CONTAINER_ARCHITECTURE}-v${ECS_CLI_VERSION} \
    && chmod +x /usr/local/bin/ecs-cli

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

RUN npm install -g yarn webpack webpack-cli

ADD requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt