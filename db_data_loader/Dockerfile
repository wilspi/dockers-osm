FROM alpine:3.12

RUN apk update
RUN apk add --no-cache git

RUN mkdir /src && cd /src && \
    git clone git://github.com/openstreetmap/osm2pgsql.git

RUN apk add --no-cache make cmake g++ boost-dev boost-filesystem expat-dev \
    zlib-dev libbz2 libpq geos proj-dev lua5.2 lua5.2-dev bzip2-dev postgresql-dev

RUN cd /src/osm2pgsql && \
    mkdir build && cd build && \
    cmake -DLUA_LIBRARY=/usr/lib/lua5.2/liblua.so ..

RUN cd /src/osm2pgsql/build && \
    make && \
    make install

#ENTRYPOINT ["mysql"]