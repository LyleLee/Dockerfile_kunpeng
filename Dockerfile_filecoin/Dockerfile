FROM golang:1.14.6 AS golang

FROM lixianfadocker/ubuntu_dev:latest
LABEL maintainer="lixianfa.official@gmail.com"
ENV REFRESHED_AT 2020-04-18

USER root
RUN apt update && apt install -y mesa-opencl-icd ocl-icd-opencl-dev gcc git bzr jq pkg-config curl && \
    apt install -y graphviz && apt clean

#a fance way to install go
COPY --from=golang /usr/local/go /usr/local/go
ENV PATH="$PATH:/usr/local/go/bin"



USER banana

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y --verbose --default-toolchain none
ENV PATH="${PATH}:/home/banana/.cargo/bin/"
RUN rustup toolchain install stable && rustup run stable rustc --version
RUN rustup toolchain install nightly && rustup run nightly rustc --version


ARG GOPROXY
ARG GO111MODULE
RUN go env -w GO111MODULE=${GO111MODULE} && go env -w GOPROXY=${GOPROXY}
