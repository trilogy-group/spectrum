FROM ubuntu:18.04

LABEL description="This file generates a docker image containing all necessary components to build and run Spectrum"

RUN apt-get update && apt-get -y install wget git gnupg libcurl4 libprotobuf10 redis-server curl software-properties-common && \
    wget https://github.com/srh/rethinkdb/releases/download/v2.3.6.srh.1/rethinkdb_2.3.6.srh.1.0bionic_amd64.deb && \
    dpkg -i /rethinkdb_2.3.6.srh.1.0bionic_amd64.deb && \
    cp /etc/rethinkdb/default.conf.sample /etc/rethinkdb/instances.d/instance1.conf && \
    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    curl -sL https://deb.nodesource.com/setup_11.x | bash - && \
    apt-get update && apt-get install -y yarn nodejs && \
    apt-get clean

WORKDIR /data

cmd tail -f /dev/null

