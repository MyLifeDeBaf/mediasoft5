create table if not exists users
(
    id          serial primary key,
    name        varchar(255)        not null default '',
    last_name   varchar(255)        not null default '',
    work        varchar(255)        not null default '',
    email       varchar(255) UNIQUE not null default '',
    work_id     int,
    users_id    int,
    price       NUMERIC,
    UNIQUE (email)

);

create table if not exists works
(
    id          serial primary key,
    works_name  varchar(255) not null default '',
    status      bool
);

create table if not exists timing
(
    id      serial primary key,
    code    varchar(255) not null default '',
    track   uuid,
    work_id int,
    user_id int
);

insert into users (name, last_name, email, price)
VALUES ('vasya', 'pupkin', 'vasya@mail.ru', '45000'),
       ('mihail', 'ryabov', 'mihail.ryabov.2002@mail.ru', '35000'),
       ('anton', 'ershov', 'ahtoika12@gmail.com', '58000'),
       ('jenya', 'pochkin', 'pochka@mail.ru', '64000'),
       ('vova', 'kursanov', 'vovak@mail.ru', '40000'),
       ('egor', 'biridze', 'egor.biridze@mail.ru', '27000');

select DISTINCT id, name, last_name, email, price from users;


select DISTINCT id, name, last_name,email,price
from users where last_name = 'pochkin';

select DISTINCT id, name, last_name,email,price
from users where name != 'egor';



