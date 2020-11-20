FROM ubuntu:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y hugo git

RUN rm -rf /hugo && \
    mkdir -p /hugo && \
    rm -rf /hugo-logs && \
    mkdir -p /hugo-logs
WORKDIR /hugo
RUN git clone https://github.com/sensorgnome-org/sensorgnome-website.git && \
    cd sensorgnome-website && \
    git submodule add https://github.com/zwbetz-gh/vanilla-bootstrap-hugo-theme.git themes/vanilla-bootstrap-hugo-theme