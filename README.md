# laravel-mysql-dev-starter
docker-based laravel development environment with mysql

# Before Build
## If wanted to change sql config:
1. Look for ./src/.etc
2. Modify the following section:
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret

# How to Build
Run:
docker-compose build && docker-compose up -d

# After Built
## Test:
http://localhost:8080

## Database Migrate:
docker-compose exec php php /var/www/html/artisan migrate

