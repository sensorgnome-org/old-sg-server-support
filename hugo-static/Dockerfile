FROM ubuntu:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y hugo git

RUN rm -rf /hugo && mkdir -p /hugo
WORKDIR /hugo
RUN git clone https://github.com/sensorgnome-org/sensorgnome-website.git
COPY ./ /hugo