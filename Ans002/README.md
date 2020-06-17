# devops_test

First of all create a compose file.

Such as docker-compose.yml 
```sh
version: "3"
services:

  web:
    image: hello-world
    ports:
      - "8085:80"
    restart: always


```


Numbers are specified as arguments in the form service=num. For example:
```sh
$ docker-compose up -d --scale web=3
```
