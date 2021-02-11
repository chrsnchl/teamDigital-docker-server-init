docker-compose exec db bash
mysql -u root -p
show databases;
GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';
FLUSH PRIVILEGES;
EXIT;
exit

docker-compose exec app php artisan migrate
docker-compose exec app php artisan tinker
\DB::table('migrations')->get();
