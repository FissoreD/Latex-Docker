FROM ubuntu:22.04

RUN apt-get -y update \
    && apt-get install -y software-properties-common \
    && apt-get -y update \
    && add-apt-repository universe
RUN apt-get -y update
RUN apt-get -y install python3
RUN apt-get -y install python3-pip
RUN apt-get -y install make
RUN apt-get -y install wget
RUN apt-get -y install perl-modules
RUN apt-get -y install libfontconfig1
RUN pip3 install pygments

RUN wget "https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2025/install-tl-unx.tar.gz"
RUN tar --extract --gzip --file=install-tl-unx.tar.gz

RUN mv $(find / -type d -name 'install-tl-*') /install-tl
WORKDIR /install-tl

RUN ./install-tl --no-interaction --no-doc-install --no-src-install

ENV PATH=/usr/local/texlive/2025/bin/x86_64-linux:$PATH


VOLUME ["/data"]
WORKDIR /data

ENTRYPOINT ["make"]
