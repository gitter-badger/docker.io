# november-eleven/docker.io
# For more information: http://github.com/november-eleven/docker.io
#
# go
#
# Example :
#   docker run --rm -t -i novembereleven/go go version
#   docker run --rm -t -i -v `pwd`:/src novembereleven/go /bin/bash

# VERSION 0.1.2

FROM debian:7.4

MAINTAINER november-eleven <november-eleven.fr>

# define env
ENV HOME /root
ENV GOPATH /root/go
ENV GOROOT /usr/local/go
ENV PATH $PATH:$GOPATH/bin:$GOROOT/bin

# create go workspace
RUN mkdir -p $GOPATH
RUN mkdir -p $GOPATH/bin
RUN mkdir -p $GOPATH/pkg
RUN mkdir -p $GOPATH/src

# execute apt required operation
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y build-essential mercurial git-core subversion wget curl zip vim ca-certificates 

# make go 1.2.2 from tarball
RUN wget --no-verbose https://storage.googleapis.com/golang/go1.2.2.src.tar.gz
RUN echo "3ce0ac4db434fc1546fec074841ff40dc48c1167 *go1.2.2.src.tar.gz" | sha1sum -c -
RUN tar -v -C /usr/local -xzf go1.2.2.src.tar.gz
RUN cd /usr/local/go/src && ./make.bash --no-clean 2>&1
RUN rm go1.2.2.src.tar.gz

# removed unnecessary packages
RUN apt-get autoremove -y

# clear package repository cache
RUN apt-get clean all

# define workspace
WORKDIR /root/go
