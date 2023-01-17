FROM debian:11 AS base

RUN apt update

RUN apt install -y curl
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

# split installation
RUN apt install -y \
    redis-server \
    lsb-release \
    dnsutils \
    iputils-ping \
    netcat \
    net-tools \
    iproute2 \
    procps \
    apt-file \
    strace

WORKDIR /app

COPY ./pause.sh /app

FROM base AS development


CMD ["/app/pause.sh"]
