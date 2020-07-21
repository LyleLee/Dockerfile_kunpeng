FROM lixianfadocker/ubuntu_dev:latest
LABEL maintainer="lixianfa.official@gmail.com"
ENV REFRESHED_AT 2020-04-18

RUN apt update && apt install -y mesa-opencl-icd ocl-icd-opencl-dev gcc git bzr jq pkg-config curl && \
    apt install -y graphviz && apt clean
RUN useradd --system --create-home --shell /bin/bash -g root -G sudo -u 2000 banana && \
    echo "banana:good" |chpasswd
USER banana
ENV HOME="/home/banana"
WORKDIR "${HOME}"
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y --verbose --default-toolchain none
ENV PATH="${PATH}:${HOME}/.cargo/bin/"
RUN mkdir go && go env -w GOPATH="${HOME}/go" && printf "notice: " && go version 
RUN go env -w GO111MODULE=on && go env -w GOPROXY=https://goproxy.io,direct && go env
COPY --chown=banana:root lotus ./lotus
WORKDIR /home/banana