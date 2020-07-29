FROM ubuntu:18.04
LABEL maintainer="lixianfa.official@gmail.com"
ENV REFRESHED_AT 2020-04-18

RUN apt update && \
    apt install -y dialog apt-utils sudo bash-completion tzdata && \
    apt install -y ca-certificates pkg-config jq iproute2 iputils-ping wget curl vim rsync git openssh-server openssh-client openssh-sftp-server ssh-import-id  && \
    apt install -y gcc g++ make cmake && apt clean
RUN mkdir -p /run/sshd && echo 'root:root' |chpasswd && echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config
ENV TZ=Asia/Hong_Kong
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ARG USER=banana
ARG USER_ID=1000
ARG GROUP_ID=1000
ARG PASSWORD=good

RUN groupadd -g ${GROUP_ID} ${USER} && useradd --create-home --uid=${USER_ID} --gid=${GROUP_ID} -G sudo "${USER}" && echo "${USER}:${PASSWORD}" | chpasswd
USER "${USER}"
WORKDIR /home/"${USER}"
