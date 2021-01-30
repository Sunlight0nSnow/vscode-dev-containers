FROM ubuntu:20.04

ARG GOLANG_VERSION
ARG PACKAGE_NAME="go$GOLANG_VERSION.linux-amd64.tar.gz"

ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin

RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends ca-certificates curl fish git && \
    apt-get clean && rm -rf /tmp/* var/tmp/*

RUN curl -O https://storage.googleapis.com/golang/$PACKAGE_NAME && \
    sha256sum $PACKAGE_NAME && \
    tar -xvf $PACKAGE_NAME && \
    chown -R root:root ./go && \
    mv go /usr/local

# Install go tools
RUN go get -v golang.org/x/tools/gopls && \
    go get -v honnef.co/go/tools/... && \
    go get -v golang.org/x/tools/cmd/gorename && \
    go get -v golang.org/x/tools/cmd/goimports && \
    go get -v golang.org/x/tools/cmd/guru && \
    go get -v golang.org/x/lint/golint && \
    go get -v github.com/mdempsky/gocode && \
    go get -v github.com/cweill/gotests/... && \
    go get -v github.com/haya14busa/goplay/cmd/goplay && \
    go get -v github.com/sqs/goreturns && \
    go get -v github.com/josharian/impl && \
    go get -v github.com/davidrjenni/reftools/cmd/fillstruct && \
    go get -v github.com/uudashr/gopkgs/v2/cmd/gopkgs && \
    go get -v github.com/ramya-rao-a/go-outline && \
    go get -v github.com/acroca/go-symbols && \
    go get -v github.com/godoctor/godoctor && \
    go get -v github.com/rogpeppe/godef && \
    go get -v github.com/zmb3/gogetdoc && \
    go get -v github.com/fatih/gomodifytags && \
    go get -v github.com/mgechev/revive && \
    go get -v github.com/go-delve/delve/cmd/dlv && \
    go get -v github.com/stamblerre/gocode
