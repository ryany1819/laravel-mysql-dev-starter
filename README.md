# laravel-mysql-dev-starter
Docker-based laravel development environment with mysql.

# Pre-Built
## Create /src/.etc
1. Look for `.env.example` under `./src`
2. Find the following section:
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

4. Save as a new file named: `.env`

## Re-Generate /src/vendor folder contents
Under `/src`, run `composer update`.

# How to Build
Run:
`docker-compose build && docker-compose up -d`

# Post-Built
## Test:
http://localhost:8080

## Database Migrate:
`docker-compose exec php php /var/www/html/artisan migrate`

