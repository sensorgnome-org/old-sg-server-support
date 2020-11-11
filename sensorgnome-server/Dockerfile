FROM ubuntu:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y golang git

RUN go get github.com/fsnotify/fsnotify github.com/jbrzusto/mbus github.com/mattn/go-sqlite3

RUN rm -rf /docker-temp && mkdir -p /docker-temp && rm -rf /sensorgnome-server-software && mkdir -p /sensorgnome-server-software
WORKDIR /docker-temp
RUN cd /docker-temp && git clone https://github.com/sensorgnome-org/sensorgnome-server.git

RUN go build ./sensorgnome-server/sensorgnomeServer.go
RUN mv /docker-temp/sensorgnomeServer /sensorgnome-server-software/sensorgnomeServer
RUN rm -rf /docker-temp