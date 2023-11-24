FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get upgrade

RUN apt-get install -y \
    build-essential \
    nano \
    telnet \
    net-tools \
    postfix

RUN mv /etc/postfix/main.cf /etc/postfix/main.cf.copy

COPY conf/postfix-main.cf /etc/postfix/main.cf

EXPOSE 25
# CMD service postfix start && service dovecot start && tail -f /dev/null

CMD ["tail", "-f", "/dev/null"]
