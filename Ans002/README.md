# Run 3 replicas using Docker compose file   (Complete)

I tried my level best.

## Establish a load balancer using HAProxy to load balance them for external traffic.  (Not Complete)

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
