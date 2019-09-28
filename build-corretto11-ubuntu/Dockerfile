FROM ubuntu:18.04

ARG SSH_ADMIN_USER
ARG SSH_ADMIN_PASS

ENV DEBIAN_FRONTEND=noninteractive

RUN echo "Europe/London" | tee /etc/timezone \
    && echo "Europe/London" | tee /etc/localtime

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    tzdata \
    java-common


RUN dpkg-reconfigure --frontend noninteractive tzdata

ADD amazon-corretto-11.0.3.7.1-linux-x64.tar.gz /opt/

ENV PATH /opt/amazon-corretto-11.0.3.7.1-linux-x64/bin:$PATH

WORKDIR /app
