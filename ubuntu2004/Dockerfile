FROM ubuntu:20.04
RUN apt-get update && apt-get install -y supervisor openjdk-8-jre-headless sudo
COPY scylla-unified-package.tar.gz /
RUN mkdir /unified
RUN tar xpf scylla-unified-package.tar.gz -C /unified
RUN cd /unified && ./install.sh --supervisor --supervisor-log-to-stdout || true
RUN scylla_dev_mode_setup --developer-mode 1
ENTRYPOINT ["supervisord", "-n"]
