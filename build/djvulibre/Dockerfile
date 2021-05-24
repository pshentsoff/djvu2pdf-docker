FROM python:3-buster

LABEL maintainer="Vadim Pshentsov <pshentsoff@gmail.com>"

RUN apt-get update && apt-get -y upgrade \
    && apt-get -y install \
        djvulibre-bin \
        ocrodjvu \
        libtiff-tools

RUN apt-get -y install \
        ruby-dev \
    && gem install pdfbeads iconv

#COPY ./requirements.txt /
#RUN pip install -U pip \
#    && pip install -r /requirements.txt

WORKDIR /var/local/src

COPY ./docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
