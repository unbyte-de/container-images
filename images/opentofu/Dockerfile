FROM alpine:3.23.0@sha256:51183f2cfa6320055da30872f211093f9ff1d3cf06f39a0bdb212314c5dc7375

ENV OPENTOFU_VERSION=1.9.3

RUN mkdir /build && \
    apk add --no-cache \
      curl=8.17.0-r1 \
      bash=5.3.3-r1 \
      && \
    rm -rf /var/cache/apk/* && \
    # https://opentofu.org/docs/intro/install/alpine/
    curl --proto '=https' --tlsv1.2 -fsSL https://get.opentofu.org/install-opentofu.sh -o install-opentofu.sh && \
      chmod +x install-opentofu.sh && \
      ./install-opentofu.sh --install-method apk --opentofu-version ${OPENTOFU_VERSION} && \
      rm -f install-opentofu.sh

WORKDIR /build

ENTRYPOINT [""]
