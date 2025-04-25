FROM grababyte/alpine-base:0.12.0

ENV NVM_VERSION=v0.40.3
ENV USER=alpine

USER root

RUN \
  apk update && \
  apk add --no-cache \
    bash==5.2.37-r0 \
    nodejs==22.13.1-r0 \
    yarn==1.22.22-r1

USER "${USER}"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN curl -o- "https://raw.githubusercontent.com/nvm-sh/nvm/${NVM_VERSION}/install.sh" | bash

ENV NVM_DIR="/home/${USER}/.nvm"
