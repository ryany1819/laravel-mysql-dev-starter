# laravel-mysql-dev-starter
Docker-based Laravel development environment with nginx/mysql.

# Pre-Built

## (optional) Clean-up old containers
Run `docker rm -f $(docker ps --filter 'name=nginx|mysql|php' -q)`

## Create new Laravel project
Laravel project root is designated to be `/src`.
Run `composer create-project laravel/laravel src` will createe a new Laravel project under `./src` folder.

## Modify database settings in `/src/.etc`
1. Open `./src/.etc`
2. Locate the following section:
```sh
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```
3. Modify to the following:
```sh
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```

# How to Build
At folder root, where `docker-compose.yml` resides, run:
`docker-compose build && docker-compose up -d`

# Post-Built

## (optional) Re-Generate /src/vendor folder contents
Under `./src`, run `composer update`.

## Database Migrate:
`docker-compose exec php php /var/www/html/artisan migrate`

# Test:
http://localhost:8080