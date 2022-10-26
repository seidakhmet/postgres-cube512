FROM postgres:14.5-bullseye

RUN apt-get update && apt-get install -y build-essential curl postgresql-server-dev-14
RUN curl https://ftp.postgresql.org/pub/source/v14.5/postgresql-14.5.tar.bz2 -o /postgresql-14.5.tar.bz2
RUN cd / && tar xvf postgresql-14.5.tar.bz2
RUN cd /postgresql-14.5/contrib/cube && sed -i 's/#define CUBE_MAX_DIM (100)/#define CUBE_MAX_DIM (512)/' cubedata.h && \
    USE_PGXS=true make && USE_PGXS=true make install

COPY create_cube_extenstion_512dim.sql /docker-entrypoint-initdb.d/
