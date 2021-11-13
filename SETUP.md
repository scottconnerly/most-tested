Getting this project to baseline from scratch
```
# Establishing the app and framework
# https://laravel.com/docs/8.x/sail
curl -s "https://laravel.build/example-app" | bash
./vendor/bin/sail up -d
docker ps
docker exec -it most-tested_laravel.test_1 bash
php artisan migrate

# Installing the login page library
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
Because this application framework loves tests, it comes packaged with some PHP
tests and tooling already! At this state, though, there's no JavaScript present,
so nothing to test, so no packaged JS testing tools yet.

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

### How Auth Works at This Point
* Breeze Controllers: app/Http/Controllers/Auth/*
* guarded by Web Sessions: \Illuminate\Auth\SessionGuard
* using users from Eloquent ORM: \Illuminate\Auth\EloquentUserProvider

The framework does have its own tests for the latter two bullets, but they are
not distributed when you install the framework. Some I'd classify as Unit 
tests, some as Integration tests. If you want to see them, they can be found
[here](https://github.com/laravel/framework/tree/8.x/tests/Auth).
