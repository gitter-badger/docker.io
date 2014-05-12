# november-eleven/docker.io
# For more information: http://github.com/november-eleven/docker.io
#
# gox
#
# Example :
#   docker run --rm -t -i novembereleven/gox go version
#   docker run --rm -t -i -v `pwd`:/src novembereleven/gox /bin/bash -c "gox-docker /src github.com/example/go"

# VERSION 0.1.0

FROM novembereleven/go:latest

MAINTAINER november-eleven <november-eleven.fr>

# get gox for go cross compilation platform
RUN go get github.com/mitchellh/gox
RUN gox -build-toolchain

# write docker wrapper
ADD ./gox-docker /usr/local/bin/gox-docker
RUN chmod 0744 /usr/local/bin/gox-docker
