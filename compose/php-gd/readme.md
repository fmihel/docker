
includes

PHP 7.4, GD, xdebug


run/done
```bash
$ docker compose up/done
```


connect
```bash
$ docker exec -it $(docker ps | grep php-gd | cut -c 1-5) /bin/bash
```


url test 
```
http://localhost:8080/
```

images
1. [php-gd](../../images/php-gd/readme.md)
