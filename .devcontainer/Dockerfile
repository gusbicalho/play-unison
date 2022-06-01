# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.233.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version (use bullseye on local arm64/Apple Silicon): bullseye, buster
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    wget iproute2 procps lsb-release

ARG UCM_DIR=/opt/unison-language
ARG UCM_ARCHIVE_NAME=ucm-linux.tar.gz
ARG UCM_ARCHIVE_URL=https://github.com/unisonweb/unison/releases/download/latest/$UCM_ARCHIVE_NAME

RUN mkdir -p $UCM_DIR \
    && wget -P $UCM_DIR $UCM_ARCHIVE_URL \
    && tar -C $UCM_DIR -xzf $UCM_DIR/$UCM_ARCHIVE_NAME \
    && ln -s $UCM_DIR/ucm /usr/bin/ \
    && rm $UCM_DIR/$UCM_ARCHIVE_NAME
