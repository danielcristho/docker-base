FROM ubuntu:18.04 as base

LABEL maintainer="@danielcristho"

RUN apt-get update && apt-get install -y build-essential

# Build for amd64 arch
FROM base as amd64

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y net-tools tcpdump telnet traceroute curl iperf3 knot-host openssh-clien openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano  \
    && rm -rf /var/lib/apt/lists/*

# VOLUME [/root]

# Build for amd64 arch
FROM base as arm64

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y net-tools tcpdump telnet traceroute curl iperf3 knot-host openssh-clien openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano  \
    && rm -rf /var/lib/apt/lists/*

# VOLUME [/root]

# Combine the platforms
COPY --from=amd64 / /
COPY --from=arm64 / /

# COPY supervisord.conf ${supervisor_conf}
# COPY start.sh /start.sh
# CMD ["/bin/bash", "/start.sh"]

# CMD ["tail", "-f", "/dev/null"]

CMD ["bash"]
# CMD ["sh", "-c", "cd; exec bash -i"]