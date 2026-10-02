FROM registry.hub.docker.com/library/python:3.14.8-alpine3.23@sha256:e8f2d5363ff792d4d9450f177cd7b9717a7915c3b7417d00557bf724e712f78d

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
