FROM registry.hub.docker.com/library/python:3.15.2-alpine3.23@sha256:4b777652b7ca0a1fae98a847e83e538605d0fb8de3812f3403076aca74368e74

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
