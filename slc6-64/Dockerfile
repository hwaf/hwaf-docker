## create a ScientificLinux CERN container from the Centos one
FROM centos
MAINTAINER binet@cern.ch

RUN rpm -ivh --force ftp://linuxsoft.cern.ch/cern/slc6X/x86_64/SLC/Packages/sl-release-6.4-1.slc6.x86_64.rpm

ADD dot-bashrc                    /root/.bashrc
ADD dot-bash_profile              /root/.bash_profile
ADD yum-repos-d-slc6-os.repo      /etc/yum.repos.d/slc6-os.repo
ADD yum-repos-d-slc6-updates.repo /etc/yum.repos.d/slc6-updates.repo
ADD yum-repos-d-slc6-extras.repo  /etc/yum.repos.d/slc6-extras.repo

RUN yum -y erase centos-release
RUN yum -y erase all
RUN yum -y distro-sync

ENV HOME /root

## EOF
