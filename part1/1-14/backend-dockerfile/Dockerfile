FROM ubuntu

EXPOSE 8080

ENV PORT=8080

ENV REQUEST_ORIGIN=http://localhost:3000

WORKDIR /usr/src/app

RUN apt-get update -y

RUN DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata

ENV TZ=Europe/Moscow

RUN apt-get install gcc make -y

RUN apt-get install wget -y

RUN wget https://dl.google.com/go/go1.15.linux-amd64.tar.gz

RUN rm -rf /usr/local/go && tar -C /usr/local -xzf go1.15.linux-amd64.tar.gz

ENV PATH=$PATH:/usr/local/go/bin

COPY . .

RUN go build .

CMD ["./server"]

