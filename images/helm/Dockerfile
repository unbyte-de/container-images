FROM registry.hub.docker.com/library/python:3.13.11-alpine3.23@sha256:2f607129b1b915a949320bf0c4831a73d1c1b1be663c2b1d8c93aa35a5f44a95

RUN mkdir /build

RUN apk add --no-cache \
    bash=5.3.3-r1 \
    curl=8.17.0-r1 \
    make=4.4.1-r3 \
    helm=3.19.0-r2 \
    git=2.52.0-r0 \
    && \
    rm -rf /var/cache/apk/*

WORKDIR /build

RUN pip install --no-cache-dir \
      yamllint==1.35.1

ENTRYPOINT [""]
