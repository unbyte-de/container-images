FROM alpine/helm:3.21.0@sha256:626f82264aa9b9ab9e232eb94e8c240bcc373bff7a29a20c848105e3a6f64b0e

# renovate: datasource=github-releases depName=kubernetes/kubernetes
ENV KUBECTL_VERSION=1.35.9

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
