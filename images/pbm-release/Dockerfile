FROM alpine:3.23.4@sha256:5b10f432ef3da1b8d4c7eb6c487f2f5a8f096bc91145e68878dd4a5019afde11

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
