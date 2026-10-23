FROM registry.hub.docker.com/library/python:3.15.1-alpine3.23@sha256:cb295b554dbbea09b2c0e6e6d9ce55f051347c902fbb611e618c071addfb30a3

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
