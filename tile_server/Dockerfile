FROM python:3.8.4-alpine

RUN apk update
RUN apk add --no-cache git

#RUN apk add --repository https://pkgs.alpinelinux.org/package/edge/testing --no-cache mapnik-dev

RUN apk add --repository http://dl-cdn.alpinelinux.org/alpine/edge/main --no-cache py3-psycopg2 && \
    apk update && apk add --no-cache autoconf apache2-dev libtool libxml2-dev libbz2 geos proj-dev \
    gdal && \
    python -m pip install --upgrade pip setuptools wheel && \
    python -m pip install mapnik
    #mapnik-dev python-mapnik python3-psycopg2