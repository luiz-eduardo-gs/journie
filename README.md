## Setup

### Environment

* `cp .env.example .env`

```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=journie
DB_USERNAME=laraveluser
DB_PASSWORD=your_laravel_db_password
```

* `docker compose up -d`
* `docker compose exec app composer install`
* `docker compose exec app php artisan key:generate`
* `docker compose exec app php artisan config:cache`

### MySQL

* `docker compose exec db bash`
* `mysql -u root -p`
* `GRANT ALL ON journie.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';`
* `FLUSH PRIVILEGES;`

### Migrations

* `php artisan config:clear`
* `docker compose exec app php artisan migrate`

## Reference

* [DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose-on-ubuntu-20-04)