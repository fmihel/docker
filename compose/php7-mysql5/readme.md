includes
```
PHP 7.4, mysql, phpmyadmin, xdebug
```

run
```bash
$ docker compose up
```

done
```bash
$ docker compose down
```

connect
```bash
$ docker exec -it $(docker ps | grep php7.4 | cut -c 1-5) /bin/bash
```