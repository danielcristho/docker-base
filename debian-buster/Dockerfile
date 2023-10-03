FROM debian:buster as base
LABEL maintainer="@danielcristho"

VOLUME /root

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y net-tools build-essential tcpdump telnet traceroute curl iperf3 knot-host openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano  \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get clean && \
    apt-get autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/cache/* && \
    rm -rf /var/lib/log/*

CMD ["bash"]