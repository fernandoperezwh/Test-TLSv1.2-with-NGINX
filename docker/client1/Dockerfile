FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y \
        build-essential \
        curl \
        nano

WORKDIR /app

CMD ["tail", "-f", "/dev/null"]
