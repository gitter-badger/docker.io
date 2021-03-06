# Gox Container

### Introduction

This docker container is provided with a go cross compilation platform: gox.

### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/novembereleven/gox/) from public [Docker Registry](https://index.docker.io/): `docker pull novembereleven/gox`

### Usage

```
docker run --rm -t -i -v `pwd`:/src novembereleven/gox /bin/bash -c "gox-docker /src github.com/example/go"
```

### Bugs / Contributing

**Any kind of feedback is highly appreciated !**

Make contributions the usual way through [GitHub](https://github.com/november-eleven/docker.io), request changes and ask questions in comments below or [email me directly](https://github.com/november-eleven/)

### Version
* **go:** 1.3.1
* **debian:** 7.6
