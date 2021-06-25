FROM centos:7
RUN yum install -y epel-release
RUN yum install -y supervisor java-1.8.0-openjdk-headless sudo
COPY scylla-unified-package.tar.gz /
RUN mkdir /unified
RUN tar xpf scylla-unified-package.tar.gz -C /unified
RUN cd /unified && ./install.sh --supervisor --supervisor-log-to-stdout
RUN scylla_dev_mode_setup --developer-mode 1
ENTRYPOINT ["supervisord", "-n"]
