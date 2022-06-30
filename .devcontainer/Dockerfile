# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.238.0/containers/cpp/.devcontainer/base.Dockerfile

# [Choice] Debian / Ubuntu version (use Debian 11, Ubuntu 18.04/22.04 on local arm64/Apple Silicon): debian-11, debian-10, ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

WORKDIR /usr/local/src/RX-ToolChain/source

RUN wget https://llvm-gcc-renesas.com/downloads/d.php?f=rx/gcc/8.3.0.202202-gnurx/gcc-8.3.0.zip -O gcc-8.3.0.zip \
    && unzip gcc-8.3.0.zip \
    && mv gcc-8.3.0 gcc

RUN wget https://llvm-gcc-renesas.com/downloads/d.php?f=rx/newlib/8.3.0.202202-gnurx/newlib-4.1.0.zip -O newlib-4.1.0.zip \
    && unzip newlib-4.1.0.zip \
    && mv newlib-4.1.0 newlib

RUN wget https://llvm-gcc-renesas.com/downloads/d.php?f=rx/binutils/8.3.0.202202-gnurx/binutils-2.36.1.zip -O binutils-2.36.1.zip \
    && unzip binutils-2.36.1.zip \
    && mv binutils-2.36.1 binutils
