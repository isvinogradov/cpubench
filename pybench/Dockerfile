FROM python:3.11.6
LABEL maintainer=isvinogradov@gmail.com
LABEL project=scanner

WORKDIR /scanner
COPY api /scanner/api

COPY requirements.txt /scanner/

ENV PYTHONPATH /scanner

RUN echo "deb http://ftp.us.debian.org/debian buster main non-free" >> /etc/apt/sources.list.d/fonts.list

RUN apt-get update && \
    apt-get install -y libpq-dev gcc && \
    apt-get install -y locales ttf-ubuntu-font-family && \
    apt-get install -yqq nodejs yarn xvfb

RUN pip3 install -U pip && \
    pip3 install -r /scanner/requirements.txt
