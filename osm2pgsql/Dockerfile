FROM ubuntu:16.04

RUN apt update && \
    apt -qy install wget make cmake g++ libboost-system-dev libboost-filesystem-dev libexpat1-dev zlib1g-dev libbz2-dev libpq-dev libproj-dev lua5.2 liblua5.2-dev

RUN cd /tmp && \
    wget https://github.com/openstreetmap/osm2pgsql/archive/0.94.0.tar.gz && \
    tar -xf 0.94.0.tar.gz && \
    cd osm2pgsql-0.94.0 && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make install && \
    cd / && \
    rm -rf /tmp/*

RUN apt -qy autoremove make cmake g++ gcc cpp libboost-system-dev libboost-filesystem-dev manpages && \
    apt clean && apt purge
