FROM ubuntu:12.04

MAINTAINER november-eleven <november-eleven.fr>

# env vars
ENV HOME /root
ENV GOPATH /root/go
ENV GOROOT /usr/local/go
ENV PATH $PATH:$GOPATH/bin:$GOROOT/bin

# GOPATH
RUN mkdir -p $GOPATH

# apt
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y build-essential mercurial git-core subversion wget curl zip vim ca-certificates 

# go 1.2 tarball
RUN wget --no-verbose https://storage.googleapis.com/golang/go1.2.2.src.tar.gz
RUN echo "3ce0ac4db434fc1546fec074841ff40dc48c1167 *go1.2.2.src.tar.gz" | sha1sum -c -
RUN tar -v -C /usr/local -xzf go1.2.2.src.tar.gz
RUN cd /usr/local/go/src && ./make.bash --no-clean 2>&1

# define workspace
WORKDIR $GOPATH

# removed unnecessary packages
RUN apt-get autoremove -y

# clear package repository cache
RUN apt-get clean all