FROM ubuntu:22.04

RUN apt-get update && apt-get install -y openssh-server

RUN mkdir -p /run/sshd \
    && mkdir -p /root/.ssh

COPY id_ed25519.pub /root/.ssh/authorized_keys

RUN chmod 700 /root/.ssh && \
    chmod 600 /root/.ssh/authorized_keys

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]