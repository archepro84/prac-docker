FROM ubuntu:16.04
LABEL version='1.0.0'

USER ubuntu

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install git -y

RUN mkdir /opt/app
RUN git clone https://github.com/archepro84/Simple-IaC.git /opt/app

