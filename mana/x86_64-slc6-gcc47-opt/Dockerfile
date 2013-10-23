## create a mana installation
FROM binet/slc6-64
MAINTAINER binet@cern.ch

ENV HOME /root

RUN yum -y update
RUN yum -y install \
           file which


RUN yum -y install binutils-devel

RUN yum -y install gcc gcc-c++ gcc-gfortran git make patch python-devel

RUN yum -y install \
           bzip2-devel \
           libXpm-devel libXft-devel libXext-devel \
           libxml2-devel \
           libuuid-devel \
           ncurses-devel \
           texinfo

RUN (cd /usr && curl -L http://cern.ch/hwaf/downloads/tar/hwaf-20131015-linux-amd64.tar.gz | tar -zxf -)

RUN hwaf version

RUN mkdir -p /build/mana
RUN (cd /build/mana && curl -L http://cern.ch/mana-fwk/downloads/src/mana-latest-next.tar.gz | tar --strip-components 1 -zxf -)

RUN (cd /build/mana && ./scripts/build-release)

## EOF
