
docker run --rm -v $(pwd):/app composer install
sudo chown -R erbi:erbi ~/laravel-proxy


# 2 - Creating the Docker Compose File
# 3 — Persisting Data
# 4 - Creating the Dockerfile
# 5 — Configuring PHP
# 6 — Configuring Nginx
# 7 — Configuring MySQL

# 8 — Modifying Environment Settings and Running the Containers
```
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan config:cache
```

# 9 — Creating a User for MySQL
```
docker-compose exec db bash
```

```
mysql -u root -p
show databases;
GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'laravel_pass';
FLUSH PRIVILEGES;
EXIT;

```

# 10 — Migrating Data and Working with the Tinker Console

```
docker-compose exec app php artisan migrate
docker-compose exec app php artisan tinker

\DB::table('migrations')->get();


```