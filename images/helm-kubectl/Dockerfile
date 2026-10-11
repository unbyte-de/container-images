FROM alpine/helm:3.22.0@sha256:70ed3f7b02ab2eee12aa520ad6870305db8a82516b07aff62f5656c657a26e2a

# renovate: datasource=github-releases depName=kubernetes/kubernetes
ENV KUBECTL_VERSION=1.34.12

SHELL ["/bin/ash", "-eo", "pipefail", "-c"]

RUN mkdir /build && \
    apk add --no-cache \
      bash=5.3.3-r1 \
      curl=8.22.0-r0 \
      yq-go=4.49.2-r6 \
      jq=1.8.2-r0 \
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
