# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.238.0/containers/cpp/.devcontainer/base.Dockerfile

# [Choice] Debian / Ubuntu version (use Debian 11, Ubuntu 18.04/22.04 on local arm64/Apple Silicon): debian-11, debian-10, ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

ARG RXINSTALLER="gcc-8.3.0.202202-GNURX-ELF.run"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    libboost-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="/opt/toolchains/bin:${PATH}"

COPY ./${RXINSTALLER} /tmp/

RUN mkdir -p /home/vscode/toolchains/ \
    && chmod +x /tmp/${RXINSTALLER} \
    && /tmp/${RXINSTALLER} -y -p /opt/toolchains \
    && rm /tmp/${RXINSTALLER}

RUN git clone --depth 1 https://github.com/Hiroya-W/RX.git -b rx_prog-RX631 /tmp/RX \
    && cd /tmp/RX/rxprog \
    && make \
    && make install \
    && rm -rf /tmp/RX
