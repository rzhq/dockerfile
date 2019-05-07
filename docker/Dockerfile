FROM docker:stable

RUN set -xe && \
    apk upgrade --update && \
    apk add --no-cache \
        build-base \
        gcc \
        libffi-dev \
        openssl-dev \
        python-dev \
        py-pip \
    && \
    pip install docker-compose && \
    touch /var/log/lastlog

