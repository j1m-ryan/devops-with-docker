FROM ubuntu

EXPOSE 5000

ENV REACT_APP_BACKEND_URL=http://example.com

WORKDIR /usr/src/app

RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -

RUN apt-get update -y

RUN DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata

ENV TZ=Europe/Moscow


RUN apt-get install -y nodejs \ 
    npm



COPY . .

RUN npm install

RUN npm run build

RUN npm install -g serve

CMD ["serve", "-s" ,"-l" ,"5000" ,"build"]



