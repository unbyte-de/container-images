FROM powerdns/pdns-auth-49:4.9.15@sha256:8fa70ccc8c0d9c8d4bb6cb4459ee7da22ac0b0da126a98f5dcec27fc4244cf8c

USER root

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    curl=7.74.0-1.3+deb11u15 && \
    # # debugging tools
    # dnsutils=1:9.16.50-1~deb11u2 \
    # tcpdump=4.99.0-2+deb11u1 \
    # procps=2:3.3.17-5 \
    # net-tools=1.60+git20181103.0eebece-1+deb11u1 && \
  apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Default DNS ports
EXPOSE 8052/udp
EXPOSE 8052/tcp
# Default webserver port
EXPOSE 8081/tcp

USER pdns
