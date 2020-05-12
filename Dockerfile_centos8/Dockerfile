FROM centos:centos8
ENV REFRESHED_AT 2020-05-12
RUN dnf clean all && dnf makecache
RUN dnf install -y glibc-langpack-en yum-utils epel-release
#RUN yum install -y gcc gcc-c++ pcre-devel zlib-devel unzip libtool openssl openssl-libs openssl-devel patch hostname libyaml clang \
#    make cmake libmaxminddb libmaxminddb-devel luarocks wget curl
RUN mkdir -p /mnt/repo
VOLUME /mnt/repo
#RUN reposync -p /mnt/repo --download-metadata --repo=AppStream && reposync -p /mnt/repo --download-metadata --repo=BaseOS && reposync -p /mnt/repo --download-metadata --repo=epel
RUN yum clean all
