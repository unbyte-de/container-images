FROM alpine/helm:3.21.0@sha256:626f82264aa9b9ab9e232eb94e8c240bcc373bff7a29a20c848105e3a6f64b0e

# TODO renovate
ENV KUBECTL_VERSION=1.31.12

SHELL ["/bin/ash", "-eo", "pipefail", "-c"]

RUN mkdir /build && \
    apk add --no-cache \
      bash=5.2.37-r0 \
      curl=8.14.1-r2 \
      yq=4.47.2-r1 \
      jq=1.8.1-r0 \
      && \
    rm -rf /var/cache/apk/* && \
    curl -s -LO "https://dl.k8s.io/release/v$KUBECTL_VERSION/bin/linux/amd64/kubectl" && \
    curl -s -LO "https://dl.k8s.io/release/v$KUBECTL_VERSION/bin/linux/amd64/kubectl.sha256" && \
    echo "$(cat kubectl.sha256)  kubectl" | sha256sum -c && \
    install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl && \
    rm -f kubectl.sha256 && \
    apk del curl

WORKDIR /build

ENTRYPOINT [""]
