#
#--------------------------------------------------------------------------
# Image Setup
#--------------------------------------------------------------------------
#

ARG BASE_IMAGE_TAG_PREFIX
ARG BASE_IMAGE_TAG_PREFIX=latest
FROM ubuntu:${BASE_IMAGE_TAG_PREFIX}

LABEL maintainer="Wp-Otto <wxp3710@gmail.com>"

# Start as root
USER root

# Install base tools
RUN apt-get update && \
    apt-get install -y tar wget curl vim git

# Install go environment 
ARG GO_VERSION
ARG GO_VERSION=1.15
ARG GO111MODULE
ARG GO111MODULE=auto
ARG GO_PACKAGE_URL=https://golang.org/dl/go${GO_VERSION}.linux-amd64.tar.gz
RUN wget ${GO_PACKAGE_URL} && \
    tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz && \
    rm go${GO_VERSION}.linux-amd64.tar.gz && \
    echo "" >> ~/.bashrc && \
    echo export GO111MODULE=${GO111MODULE} >> ~/.bashrc && \
    echo export GOROOT=/usr/local/go  >> ~/.bashrc && \
    echo export GOPATH=~/go >> ~/.bashrc && \
    echo export GOBIN=~/go/bin >> ~/.bashrc && \
    echo export PATH="$"PATH:/usr/local/go/bin >> ~/.bashrc && \
    echo "" >> ~/.bashrc && \
    echo "go workspace build complete!"




