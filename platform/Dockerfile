FROM alpine:3.14

# SUDO
RUN apk --update add sudo

# SSH client
RUN apk --update add sshpass openssh-client rsync cargo

# Python
RUN apk --update add python3 py3-pip openssl ca-certificates && \
    apk --update add --virtual build-dependencies python3-dev libffi-dev openssl-dev build-base && \
    pip install --upgrade pip cffi

# Ansible
RUN pip install ansible

# Clean up
RUN apk del build-dependencies && \
    rm -rf /var/cache/apk/*

WORKDIR /etc/ansible/env/dev
