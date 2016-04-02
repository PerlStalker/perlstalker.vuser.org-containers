FROM ubuntu:trusty
MAINTAINER Randall Smith <perlstalker@gmail.com>

RUN apt-get update

RUN apt-get install -y perl cpanminus build-essential git libssl-dev && apt-get clean

WORKDIR /usr/local/src/
RUN git clone https://github.com/PerlStalker/comics-fetcher.git
WORKDIR /usr/local/src/comics-fetcher/

RUN perl ./Build.PL
RUN ./Build installdeps
RUN ./Build install

# copy in fetcher config
ADD fetcher.conf /usr/local/etc/

ENTRYPOINT /usr/local/bin/fetcher

