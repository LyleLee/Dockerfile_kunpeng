FROM centos:7
ENV REFRESHED_AT 2020-04-27
COPY CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo
RUN yum clean all && yum makecache
RUN yum install -y gcc gcc-c++ pcre-devel zlib-devel unzip libtool openssl openssl-libs openssl-devel patch hostname libyaml clang \
    make cmake  wget curl git
RUN yum clean all


