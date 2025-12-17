FROM powerdns/pdns-auth-49:4.9.5@sha256:f8afaab7cd37b34d3e38e6a23d568e564d310fc6203d456f505e1ad3f5b34bba

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
