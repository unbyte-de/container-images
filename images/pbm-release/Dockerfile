FROM alpine:3.24.4@sha256:f59abe656b692d901e184be3445e084786602108599d2a51d229c0f5a48c71bf

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
