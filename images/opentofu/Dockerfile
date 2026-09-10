FROM alpine:3.24.1@sha256:28bd5fe8b56d1bd048e5babf5b10710ebe0bae67db86916198a6eec434943f8b

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
