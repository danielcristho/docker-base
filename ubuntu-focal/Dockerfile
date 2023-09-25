FROM ubuntu:20.04 as base

LABEL maintainer="@danielcristho"

VOLUME /root

# Build for amd64 arch
# FROM base as amd64

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y net-tools build-essential tcpdump telnet traceroute curl iperf3 knot-host openssh-client openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano  \
    && rm -rf /var/lib/apt/lists/*

### Clear cache and change shell ###
RUN apt-get clean && \
    apt-get autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/cache/* && \
    rm -rf /var/lib/log/*

# # Build for amd64 arch
# FROM base as arm64

# RUN DEBIAN_FRONTEND=noninteractive \
#     apt-get update \
#     && apt-get install -y net-tools tcpdump telnet traceroute curl iperf3 knot-host openssh-clien openssh-server mtr-tiny socat nmap iputils-ping rsyslog vim iptables iproute2 nano  \
#     && rm -rf /var/lib/apt/lists/*

# ### Clear cache and change shell ###
# RUN apt-get clean && \
#     apt-get autoclean && \
#     apt-get autoremove -y && \
#     rm -rf /var/lib/cache/* && \
#     rm -rf /var/lib/log/* &&

# # Combine the platforms
# COPY --from=amd64 / /
# COPY --from=arm64 / /

# COPY supervisord.conf ${supervisor_conf}
# COPY start.sh /start.sh
# CMD ["/bin/bash", "/start.sh"]

# CMD ["tail", "-f", "/dev/null"]

CMD ["bash"]
# CMD ["sh", "-c", "cd; exec bash -i"]