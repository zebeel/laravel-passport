## Install laravel and passport
- $ laravel new laravel-passport
- $ composer require laravel/passport
- $ php artisan migrate
- $ php artisan passport:install

## Config passport and make model, controller, api
- Add HasApiTokens to User model
- Add Passport::routes(); to AuthServiceProvider
- Change drive of api to passport in config/auth.php
- Create Test model with migration: $ php artisan make:migration Test
- Then migrate new change: $ php artisan migrate
- Make controller: $ php artisan make:controller API/AuthController
> This controller allows creating new user or login by registered user. Check the response and keep the token for authentication.
- Make Test controller: $ php artisan make:controller API/TestController
> This controller includes the CRUD operation for Test model. When api called, procession goes here.
- Add route for api in api.php
- Test api. Can see all route by command: $ php artisan route:list
> Firstly, create new user if not exist then copy the token in response or login by an existing user and copy the token.
>
> When access any API which authentication is required, put token to the HTTP Header by set the value of Authorization parameter with received token.
> 
>For ex. Authorization: Bearer {token here without {}}
