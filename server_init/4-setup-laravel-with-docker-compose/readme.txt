# https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose

cd ~
git clone https://github.com/laravel/laravel.git laravel-app

cd ~/laravel-app

docker run --rm -v $(pwd):/app composer install

sudo chown -R $USER:$USER ~/laravel-app

----------------------

copy the files from, 'upload_these_files_to_server_inside_laravel_app'
put the files in ~/laravel-app

# use env_truncated.txt as a guide
cp ~/laravel-app/.env.example ~/laravel-app/.env
nano .env

sudo docker-compose up -d
docker ps
# You will see the output with details about your app, webserver, and db containers:

    # pitfall:
    # Fatal error: Composer detected issues in your platform: Your Composer dependencies require a PHP version ">= 7.3.0". You are running 7.2.34. in /var/www/vendor/composer/platform_check.php on line 24
    # fix: Update Dockerfile to use PHP version: 
    # FROM php:7.3-fpm

    #pitfall
    # added libzip-dev to the list of installations in Dockerfile

sudo docker-compose exec app php artisan key:generate

# sudo docker-compose exec app php artisan config:cache 
# don't enable cache during development, it will become confusing







