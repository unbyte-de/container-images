FROM powerdns/pdns-auth-49:4.9.20@sha256:2d0245f6462b4162d515f6966f4e51bf26e8416ac795ea3d51e42956783cffcb

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
