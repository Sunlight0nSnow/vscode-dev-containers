FROM ubuntu:20.04

ARG TYPESCRIPT_VERSION="4"

# Install npm
RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends npm fish && \
    apt-get clean && rm -rf /tmp/* var/tmp/* && rm -rf /var/lib/apt/lists/*

# Install typescript
RUN npm install typescript@$TYPESCRIPT_VERSION --save-dev
