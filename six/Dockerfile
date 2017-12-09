FROM alpine:3.6

ENV ALPINE_VERSION=3.6

RUN apk upgrade --update \
    && apk add --no-cache vim python2 python3 py2-pip \
    && pip2 install --upgrade pip \
    && pip3 install --upgrade pip

