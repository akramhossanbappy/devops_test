# devops_test

First of all create a compose file.

Such as docker-compose.yml 

version: "3"
services:

  web:
    image: hello-world
    ports:
      - "8085:80"
    restart: always




 
$ docker-compose up -d --scale web=3
