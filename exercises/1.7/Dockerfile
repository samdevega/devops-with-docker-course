FROM ubuntu:22.04

RUN apt-get update && apt-get -y upgrade && apt-get -y install curl

WORKDIR /usr/src/app

COPY script.sh .

RUN chmod +x script.sh

CMD ./script.sh
