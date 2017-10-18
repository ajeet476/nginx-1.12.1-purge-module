
## Dockerfile used Testing
#### Nginx with Purge module
Nginx is installed in /etc/nginx <br>
Note: nginx.service is not registered <br>
[Nginx 1.12.1 ](Dockerfile)
#### Apache Backend Server
[Apache backend](./backend/Dockerfile)



## prepare, git clone
```shell
$ git clone https://github.com/ajeet476/nginx-1.12.1-purge-module.git docker
$ cd docker
$ git clone https://github.com/ajeet476/utility.git src
```


## running container and purge test
```shell
# now run container
$ docker-compose up -d


# check for cache
$ curl localhost
$ curl localhost/purge/

```

