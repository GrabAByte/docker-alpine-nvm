FROM grababyte/alpine-base:0.11.0

ARG NODE_MAJOR_VERSION '22'

ENV NVM_VERSION 'v0.39.1'
ENV PATH "${PATH}:/.yarn/bin"
ENV USER alpine

USER root

RUN \
  apk update && \
  apk add --no-cache \
    bash==5.2.21-r0 \
    nodejs==20.15.1-r0 \
    yarn==1.22.19-r0

USER "${USER}"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/"${NVM_VERSION}"/install.sh | bash

ENV NVM_DIR "/home/${USER}/.nvm"

# hadolint ignore=SC1091
RUN \
  . "${NVM_DIR}/nvm.sh" && \
  nvm install "${NODE_MAJOR_VERSION}"
