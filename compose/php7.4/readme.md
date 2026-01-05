
includes

PHP 7.4, xdebug


run/done
```bash
$ docker compose up/done
```


connect
```bash
$ docker exec -it $(docker ps | grep php7.4 | cut -c 1-5) /bin/bash
```


url test 
```
http://localhost:8080/
```

images
1. [php7.4](../../images/php7.4/readme.md)
