FROM ubuntu:20.04

ARG RUBY_VERSION
ARG GPG_KEYS="409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB"

ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# Install rvm
RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends ca-certificates gnupg2 curl fish && \
    ( \
    gpg2 --batch --keyserver hkp://pool.sks-keyservers.net --recv-keys $GPG_KEYS || \
    gpg2 --batch --keyserver pgp.mit.edu --recv-keys $GPG_KEYS || \
    gpg2 --batch --keyserver keyserver.pgpg.com --recv-keys  $GPG_KEYS \
    ) && \
    curl -sSL https://raw.githubusercontent.com/rvm/rvm/stable/binscripts/rvm-installer -o rvm-installer && \
    curl -sSL https://raw.githubusercontent.com/rvm/rvm/stable/binscripts/rvm-installer.asc -o rvm-installer.asc && \
    gpg2 --verify rvm-installer.asc rvm-installer && \
    bash rvm-installer && \
    . /etc/profile.d/rvm.sh && rvm requirements && \
    apt-get clean && rm -rf /tmp/* var/tmp/*

# Install ruby version w/ solargraph gem for VS Code solargraph extension
RUN rvm install $RUBY_VERSION && \
    echo "source /usr/local/rvm/scripts/rvm" >> /etc/profile && \
    echo "rvm --default use $RUBY_VERSION" >> /etc/profile && \
    bash -lc "gem install solargraph"   
