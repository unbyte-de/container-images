# https://gitlab.com/to-be-continuous/pre-commit#building-your-own-pre-commit-image-1
FROM registry.hub.docker.com/library/python:3.13.11-alpine3.23@sha256:51b5354ed44df6e1a3b3faf6d3a3d40da129621046b6d5a707b7c1f44d258ed6

# TODO renovate
ENV PACKER_VERSION=1.11.2
ENV TFLINT_VERSION=0.55.0
ENV OPENTOFU_VERSION=1.9.0
ENV HADOLINT_VERSION=2.12.0

# https://github.com/hadolint/hadolint/wiki/DL4006
SHELL ["/bin/ash", "-eo", "pipefail", "-c"]

RUN mkdir /build && \
    apk add --no-cache \
      git=2.52.0-r0 \
      bash=5.3.3-r1 \
      gnupg=2.4.8-r1 \
      && \
    # Install packer
    # https://developer.hashicorp.com/well-architected-framework/operational-excellence/verify-hashicorp-binary#create-alpine-linux-container-with-hashicorp-tools
    wget -q https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
      wget -q https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_SHA256SUMS && \
      wget -q https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_SHA256SUMS.sig && \
      wget -qO- https://www.hashicorp.com/.well-known/pgp-key.txt | gpg --import && \
      gpg --verify packer_${PACKER_VERSION}_SHA256SUMS.sig packer_${PACKER_VERSION}_SHA256SUMS && \
      grep packer_${PACKER_VERSION}_linux_amd64.zip packer_${PACKER_VERSION}_SHA256SUMS | sha256sum -c && \
      unzip ./packer_${PACKER_VERSION}_linux_amd64.zip -d ./ && \
      mv ./packer /usr/local/bin/packer && \
      rm -f ./packer_* && \
      apk del gnupg && \
      rm -rf /var/cache/apk/* && \
    # https://github.com/terraform-linters/tflint?tab=readme-ov-file#installation
    wget -q https://github.com/terraform-linters/tflint/releases/download/v${TFLINT_VERSION}/tflint_linux_amd64.zip -O tflint_linux_amd64.zip && \
      unzip tflint_linux_amd64.zip -d tflint_linux_amd64 && \
      mv tflint_linux_amd64/tflint /usr/local/bin/tflint && \
    # https://opentofu.org/docs/intro/install/alpine/
    wget -q -O install-opentofu.sh https://get.opentofu.org/install-opentofu.sh && \
      chmod +x install-opentofu.sh && \
      ./install-opentofu.sh --install-method apk --opentofu-version ${OPENTOFU_VERSION} && \
      rm -f install-opentofu.sh && \
    pip install --no-cache-dir --upgrade pip==25.0 && \
    pip install --no-cache-dir pre-commit==3.5.0 && \
    wget -q https://github.com/hadolint/hadolint/releases/download/v${HADOLINT_VERSION}/hadolint-Linux-x86_64 -O hadolint-Linux-x86_64 && \
      chmod +x hadolint-Linux-x86_64 && \
      mv hadolint-Linux-x86_64 /usr/local/bin/hadolint

WORKDIR /build

# RUN cat <<EOF > hook-install-config.yaml
# repos:
#     - repo: https://github.com/pre-commit/pre-commit-hooks
#       rev: v4.5.0
#       hooks:
#         - id: no-commit-to-branch
#         - id: trailing-whitespace
#         - id: check-merge-conflict
#         - id: check-yaml
#         - id: end-of-file-fixer
#         - id: fix-byte-order-marker
#         - id: mixed-line-ending
# EOF

# COPY hook-install-config.yaml ./.pre-commit-config.yaml

# RUN git init && \
#     pre-commit install-hooks && \
#     rm ./.pre-commit-config.yaml && \
#     rm -rf .git

CMD ["--help"]

ENTRYPOINT ["pre-commit"]
