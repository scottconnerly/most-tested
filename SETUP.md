Getting this project to baseline from scratch 
```
# Establishing the app and framework
# https://laravel.com/docs/8.x/sail
curl -s "https://laravel.build/example-app" | bash
./vendor/bin/sail up -d
docker ps
docker exec -it most-tested_laravel.test_1 bash
php artisan migrate

# Installing the auth library
# https://laravel.com/docs/8.x/starter-kits#laravel-breeze
composer require laravel/breeze --dev
php artisan breeze:install
npm install && npm run dev

# Create the test user
http://localhost/register
Name: Most Tested
Email: asdf@asdf.com
Password: 3qQe4h$ABt
```
at this point, we now have access to...
## The Login Page of Destiny:
http://localhost/login

From which we can start adding all the testing apparatus.

