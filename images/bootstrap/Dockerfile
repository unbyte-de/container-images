FROM registry.hub.docker.com/library/python:3.13.11-alpine3.23@sha256:51b5354ed44df6e1a3b3faf6d3a3d40da129621046b6d5a707b7c1f44d258ed6

# TODO renovate
ENV CLUSTERCTL_VERSION=1.9.1
ENV OPENTOFU_VERSION=1.9.0
ENV HCLOUD_VERSION=1.50.0

RUN mkdir /build && \
    apk add --no-cache \
      bash=5.3.3-r1 \
      curl=8.17.0-r1 \
      helm=3.19.0-r2 \
      kubectl=1.34.2-r1 \
      kustomize=5.7.1-r4 \
      yq=4.49.2-r1 \
      jq=1.8.1-r0 \
      age=1.2.1-r10 \
      sed=4.9-r2 \
      && \
    rm -rf /var/cache/apk/* && \
    # https://cluster-api.sigs.k8s.io/user/quick-start#install-clusterctl
    curl -L https://github.com/kubernetes-sigs/cluster-api/releases/download/v${CLUSTERCTL_VERSION}/clusterctl-linux-amd64 -o clusterctl && \
      chmod +x clusterctl && \
      mv clusterctl /usr/local/bin/clusterctl && \
    # https://opentofu.org/docs/intro/install/alpine/
    curl --proto '=https' --tlsv1.2 -fsSL https://get.opentofu.org/install-opentofu.sh -o install-opentofu.sh && \
      chmod +x install-opentofu.sh && \
      ./install-opentofu.sh --install-method apk --opentofu-version ${OPENTOFU_VERSION} && \
      rm -f install-opentofu.sh && \
    # https://github.com/hetznercloud/cli
    curl -L https://github.com/hetznercloud/cli/releases/download/v${HCLOUD_VERSION}/hcloud-linux-amd64.tar.gz -o hcloud-linux-amd64.tar.gz && \
    mkdir -p /tmp/hcloud-linux-amd64 && \
    tar -xzf hcloud-linux-amd64.tar.gz -C /tmp/hcloud-linux-amd64 && \
    mv /tmp/hcloud-linux-amd64/hcloud /usr/local/bin/hcloud && \
    rm -rf hcloud-linux-amd64.tar.gz /tmp/hcloud-linux-amd64

WORKDIR /build

ENTRYPOINT [""]
