FROM registry.hub.docker.com/library/python:3.15.2-alpine3.23@sha256:32f06114a111c2467804d06194c5584f16804a78cfaf427fb1fcbb0b3391d0f1

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
