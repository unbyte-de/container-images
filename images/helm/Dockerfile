FROM registry.hub.docker.com/library/python:3.15.0-alpine3.23@sha256:70ba88b13e449304d8422f9c935c4aea5515877770235f044e0ed3af2d3574c2

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
