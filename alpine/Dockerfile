FROM alpine:latest
RUN apk add --no-cache supervisor openjdk8-jre-base sudo tar bash coreutils grep shadow
COPY scylla-unified-package.tar.gz /
RUN mkdir /unified
RUN tar xpf scylla-unified-package.tar.gz -C /unified
RUN cd /unified && ./install.sh --supervisor --supervisor-log-to-stdout
RUN scylla_dev_mode_setup --developer-mode 1
ENTRYPOINT ["supervisord", "-n"]
