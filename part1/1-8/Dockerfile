FROM ubuntu:18.04

RUN apt-get update -y 

RUN apt-get upgrade -y

RUN apt install curl -y

WORKDIR /usr/src/app

COPY script.sh .

RUN chmod +x script.sh

CMD ./script.sh