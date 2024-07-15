FROM mcr.microsoft.com/devcontainers/base:debian-12

ARG USERNAME=vscode

ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=C.UTF-8

RUN apt update \ 
    && apt install -y --no-install-recommends \
    build-essential \
    git unzip curl wget vim sudo ssh tzdata ca-certificates \
    && apt clean -y \
    && rm -rf /var/lib/apt/lists

RUN wget "https://github.com/pinterest/ktlint/releases/download/1.3.1/ktlint" \
    && chmod +x ktlint \
    && mv ktlint /usr/local/bin/

USER ${USERNAME}

SHELL [ "/bin/bash", "-c" ]
RUN curl -s "https://get.sdkman.io" | bash \
    && source "/home/${USERNAME}/.sdkman/bin/sdkman-init.sh" \
    && sdk install java 21.0.2-amzn \
    && sdk install kotlin
