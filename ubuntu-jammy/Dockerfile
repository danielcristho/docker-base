FROM ubuntu:22.04 as base

LABEL maintainer="<@danielcristho>"

VOLUME /root


ENV TZ=UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y net-tools build-essential tcpdump telnet traceroute curl iperf3 knot-host openssh-client openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano wget \
    && rm -rf /var/lib/apt/lists/*

### Clear cache and change shell ###
RUN apt-get clean && \
    apt-get autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/cache/* && \
    rm -rf /var/lib/log/*

CMD ["bash"]
# CMD ["sh", "-c", "cd; exec bash -i"]
