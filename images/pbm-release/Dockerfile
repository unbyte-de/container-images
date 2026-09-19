FROM alpine:3.24.2@sha256:294b683cb724975bec92580e1e685676bd4b50bda910ddb8c51d4cabeaec77e6

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
