FROM ubuntu:20.04

RUN apt update && apt install -y software-properties-common
RUN add-apt-repository --yes --update ppa:ansible/ansible
RUN apt install -y ansible

RUN useradd -r -u 1000 -g appuser ansible
USER ansible
