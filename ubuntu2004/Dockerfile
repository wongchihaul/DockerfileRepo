FROM amd64/ubuntu:20.04
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y vim openssh-server && \
    sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config &&\
    sed -i 's/#PubkeyAuthentication/PubkeyAuthentication/g' /etc/ssh/sshd_config &&\
    sed -i 's/#AuthorizedKeysFile/AuthorizedKeysFile/g' /etc/ssh/sshd_config &&\
    /etc/init.d/ssh restart &&\
    mkdir /root/.ssh
COPY authorized_keys /root/.ssh/
EXPOSE 22
LABEL org.opencontainers.image.authors="wongchihaul"


