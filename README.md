# AWO
Instantiate a pg DB:
=============
docker run --name awo_pg -e POSTGRES_PASSWORD=mysecretpassword -d postgres

Login to PG:
============
docker exec -it awo_pg bash


CREATE SCHEMA IF NOT EXISTS awo

create the table:
==========
create donors table
create table if not postgres.awo.donors (
    id serial primary key,
    name varchar(63) not null,
    email varchar(63) not null,
    phone BIGINT not null,
    place varchar,
    created_at timestamp default current_timestamp,
    update_at timestamp default current_timestamp,
    token varchar
); 

To connect to psql using pgadmin:
========
Launch: pgadmin and give localhost connection details. 

INSERT INTO awo.donors (name,email,phone,place) VALUES ('Navami','9mikini@gmail.com','8095791774','Donderangadi');