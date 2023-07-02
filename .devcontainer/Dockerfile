FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

ENV PATH="$PATH:/bin/flutter/bin:/bin/cmdline-tools/bin:/bin/android-studio/bin"
ARG FLUTTER_PKG="flutter_linux_3.10.5-stable.tar.xz"
ARG ANDROID_STUDIO="android-studio-2022.2.1.20-linux.tar.gz"
ARG ANDROID_STUDIO_CLI_TOOLS="commandlinetools-linux-9477386_latest.zip"

RUN dpkg --add-architecture i386 && \
  apt-get -y update && \
  apt-get -y install file curl xz-utils clang cmake ninja-build pkg-config libgtk-3-dev liblzma-dev libglu1-mesa libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386 && \
  curl -L "https://redirector.gvt1.com/edgedl/android/studio/ide-zips/2022.2.1.20/${ANDROID_STUDIO}" -o "/tmp/${ANDROID_STUDIO}" && \
  curl -L "https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/${FLUTTER_PKG}" -o "/tmp/${FLUTTER_PKG}" && \
  curl -L "https://dl.google.com/android/repository/${ANDROID_STUDIO_CLI_TOOLS}" -o "/tmp/${ANDROID_STUDIO_CLI_TOOLS}" && \
  tar xf "/tmp/${FLUTTER_PKG}" -C /bin/. && \
  tar xf "/tmp/${ANDROID_STUDIO}" -C /bin/. && \
  unzip "/tmp/${ANDROID_STUDIO_CLI_TOOLS}" -d /bin/.

USER vscode