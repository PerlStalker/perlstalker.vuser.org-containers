FROM perl:5.26

RUN cpanm \
 Module::Build

WORKDIR /usr/local/src/
RUN git clone https://github.com/PerlStalker/comics-fetcher.git
WORKDIR /usr/local/src/comics-fetcher/

RUN perl ./Build.PL && ./Build installdeps  && ./Build install

# copy in fetcher config
ADD fetcher.conf /usr/local/etc/

ENTRYPOINT /usr/local/bin/fetcher

