FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

ENV PATH="$PATH:/bin/flutter/bin"
ARG FLUTTER_PKG="flutter_linux_3.10.5-stable.tar.xz"

RUN apt-get -y update && \
  apt-get -y install curl && \
  apt-get install xz-utils && \
  curl "https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/${FLUTTER_PKG}" -o "/tmp/${FLUTTER_PKG}" && \
  tar xf "/tmp/${FLUTTER_PKG}" -C /bin/.

USER vscode