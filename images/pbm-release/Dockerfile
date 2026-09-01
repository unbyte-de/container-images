FROM alpine:3.24.1@sha256:28bd5fe8b56d1bd048e5babf5b10710ebe0bae67db86916198a6eec434943f8b

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
