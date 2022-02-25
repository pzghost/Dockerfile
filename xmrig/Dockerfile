FROM ubuntu:20.04

RUN export DEBIAN_FRONTEND=noninteractive \
    && apt update \
    && apt install -y git cmake g++ gcc libhwloc-dev libuv1 libuv1-dev libh2o-dev libuvc-dev libuvc0 libssh-dev \
    && git clone https://github.com/MoneroOcean/xmrig  /xmrig \
    && cd /xmrig \
    && cmake . \
    && make \
    && mv xmrig /usr/local/bin/ \
    && cd / \
    && rm -rf /xmrig \
    && unset DEBIAN_FRONTEND

ENTRYPOINT [ "/usr/local/bin/xmrig" ]
CMD [  "--config", "/root/moneroocean/config.json" ]
