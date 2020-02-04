# PHP 7.2 & Maria DB in docker containers

```
git clone https://github.com/x25treinamento/docker-php-mysql.git [nome_do_projeto]

cd [nomde_do_projeto]

cd docker

docker-compose up
```

## Compose

### Database (MariaDB)

...

### PHP (PHP-FPM)

Composer is included

```
docker-compose run php-fpm composer 
```

#### Symfony Project

Run this if you are building a traditional web application

```
docker-compose run php-fpm composer create-project symfony/website-skeleton .

```
Run this if you are building a microservice, console application or API
```
docker-compose run php-fpm composer create-project symfony/website-skeleton .

```



To run fixtures

```
docker-compose run php-fpm bin/console doctrine:fixtures:load
```
