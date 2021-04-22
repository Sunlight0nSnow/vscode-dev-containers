FROM ubuntu:20.04

ARG NIM_VERSION

ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/root/.nimble/bin

RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends ca-certificates curl fish git \ 
        gcc linux-libc-dev libc6-dev && \
    apt-get autoremove -y && apt-get clean && rm -rf /tmp/* var/tmp/*

ENV CHOOSENIM_CHOOSE_VERSION $NIM_VERSION

RUN curl https://nim-lang.org/choosenim/init.sh -sSf >> /home/init.sh && \
    chmod +x /home/init.sh && \
    sh /home/init.sh -y && \
    rm /home/init.sh
