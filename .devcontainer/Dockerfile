# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.238.0/containers/cpp/.devcontainer/base.Dockerfile

# [Choice] Debian / Ubuntu version (use Debian 11, Ubuntu 18.04/22.04 on local arm64/Apple Silicon): debian-11, debian-10, ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    libboost-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="/opt/toolchains/bin:${PATH}"

COPY ./gcc-8.3.0.202202-GNURX-ELF.run /tmp/

RUN mkdir -p /home/vscode/toolchains/ \
    && chmod +x /tmp/gcc-8.3.0.202202-GNURX-ELF.run \
    && /tmp/gcc-8.3.0.202202-GNURX-ELF.run -y -p /opt/toolchains
