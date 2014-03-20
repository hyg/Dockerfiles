
FROM ubuntu

MAINTAINER Huang Yonggang <fromoon@gmail.com>

RUN apt-get update

RUN apt-get -y install sudo
RUN apt-get -y install openssh-server
RUN apt-get -y install git-core
RUN echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAIB7Ae7Y7PVV4eL/6dxtrD9Ka4FlEN2I1r6g/3lievLAGBGdecnYjGNirCUxxm8MlSUmNwHbsoduA+Zw1XCyovwawVch2IzL7uJ6KBZ4i6BZaYiYeny1cIzQ6Du9g+JkkWfLbcSzuDPbrPdFqy+0hBW39WDa7Y/KVGDpXxAKt2mC8Q==" > /tmp/admin.pub
RUN apt-get -y install gitolite
RUN adduser --system --shell /bin/bash --gecos 'git version control' --group --disabled-password --home /home/git git
RUN su git
RUN echo "PATH=$HOME/bin:$PATH" > ~/.bashrc
RUN gl-setup /tmp/admin.pub

## only for Gitweb
## change $REPO_UMASK = 0077; to $REPO_UMASK = 0027;
## Add .gitolite.rc /home/git

EXPOSE 22