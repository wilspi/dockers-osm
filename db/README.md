
dockerfile: https://github.com/postgis/docker-postgis/blob/master/12-3.0/alpine

docker build .
docker run -d -e POSTGRES_PASSWORD=postgres -p 5432:5432 b97bae343e06

createuser -h 127.0.0.1 -p 5432 -U postgres -W tmuser
createdb -h 127.0.0.1 -p 5432 -U postgres -W -E UTF8 -O tmuser mapgis


psql -h 127.0.0.1 -p 5432 -U postgres -W


CREATE EXTENSION postgis;
CREATE EXTENSION hstore;
ALTER TABLE geometry_columns OWNER TO tmuser;
ALTER TABLE spatial_ref_sys OWNER TO tmuser;

