FROM ubuntu:trusty
MAINTAINER Randall Smith <perlstalker@gmail.com>

RUN apt-get update

RUN apt-get install -y perl cpanminus build-essential
RUN apt-get install -y mercurial

WORKDIR /usr/local/src/
RUN hg clone https://code.google.com/p/comics-fetcher/
WORKDIR /usr/local/src/comics-fetcher/

RUN perl ./Build.PL
RUN ./Build installdeps
RUN ./Build install

# copy in fetcher config
ADD fetcher.conf /usr/local/etc/

ENTRYPOINT /usr/local/bin/fetcher

