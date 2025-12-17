FROM alpine:3.23.0@sha256:51183f2cfa6320055da30872f211093f9ff1d3cf06f39a0bdb212314c5dc7375

RUN mkdir /build && \
    apk add --no-cache \
      bash=5.3.3-r1 \
      curl=8.17.0-r1 \
      git=2.52.0-r0 \
      yq=4.49.2-r1 \
      jq=1.8.1-r0 \
      && \
    rm -rf /var/cache/apk/*

WORKDIR /build

ENTRYPOINT [""]
