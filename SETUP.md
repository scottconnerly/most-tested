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

### Already included testing:
Because this application framework loves tests, it comes packaged with some
tests and tooling already!

#### Test Types
* PHP Feature

#### Test Runners
* PHPUnit (vendor/phpunit/phpunit)

#### PHP Test Helpers & Utilities
* Mockery (vendor/mockery/mockery)
* Prophecy (vendor/phpspec/prophecy)
* Faker (vendor/fakerphp/faker)
* Webmozart Assert (vendor/webmozart/assert)
* Code Coverage (vendor/phpunit/php-code-coverage)
* Complexity (vendor/sebastian/complexity)
* Test Timer (vendor/phpunit/php-test-timer)
* (many other lower level utilities)

#### See it in action
`php artisan test`

