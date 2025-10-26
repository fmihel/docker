includes
```
PHP 7.4, mysql, phpmyadmin, xdebug
```

build
```bash
$ docker build -t php-imagick .
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
$ docker exec -it $(docker ps | grep php-imagick | cut -c 1-5) /bin/bash
```