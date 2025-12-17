FROM powerdns/pdns-recursor-49:4.9.9@sha256:cf30d3d85b6df23c20978b92c3ac2bd1aefc6da21c68a39d9159f53fd9966978

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
EXPOSE 8053/udp
EXPOSE 8053/tcp
# Default webserver port
EXPOSE 8082/tcp

USER pdns
