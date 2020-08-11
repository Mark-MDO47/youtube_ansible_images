FROM ubuntu:18.04 as ansible_runner
ENV PS1 '$(whoami):$(pwd)\\$ '
ARG MYUSER=mdo
ARG MYPASS=mdo
ARG MYUID=1000
ARG MYGID=1000
RUN apt-get update --yes
RUN apt-get upgrade --yes
RUN echo "2x85xYxYx" | tr "x" "\n" | apt install --yes apt-transport-https ca-certificates curl software-properties-common
RUN apt-add-repository --yes --update ppa:ansible/ansible
RUN apt-get install ansible --yes
RUN apt-get install python --yes
RUN cp /etc/ansible/ansible.cfg ./ansible.cfg.tmp
RUN sed "s?^.ssh_args.*?ssh_args = -C -o ControlMaster=auto -o ControlPersist=60s -o ControlPath=/dev/shm/cp%h-%p-%r?" ./ansible.cfg.tmp > /etc/ansible/ansible.cfg
RUN addgroup --group ansible --gid ${MYGID}
RUN echo "${MYPASS}nEwLiNe${MYPASS}nEwLiNenEwLiNenEwLiNenEwLiNenEwLiNenEwLiNeYnEwLiNe" | sed "s/nEwLiNe/\n/g" | adduser --home /home/${MYUSER} --shell /bin/bash --uid ${MYUID} --gid ${MYGID} ${MYUSER}
USER ${MYUID}:${MYGID}
WORKDIR /home/${MYUSER}
