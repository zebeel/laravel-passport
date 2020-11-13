## Install laravel and passport
- $ laravel new laravel-passport
- $ composer require laravel/passport
- $ php artisan migrate
- $ php artisan passport:install

## Config passport and make a model, controller, API
- Add HasApiTokens to the User model
- Add Passport::routes(); to AuthServiceProvider
- Change drive of API to passport in config/auth.php
- Create Test model with migration: $ php artisan make:migration Test
- Then migrate new change: $ php artisan migrate
- Make controller: $ php artisan make:controller API/AuthController
> This controller allows creating new user or login by registered user. Check the response and keep the token for authentication.
- Make Test controller: $ php artisan make:controller API/TestController
> This controller includes the CRUD operation for the Test model. When API called, the procession goes here.
- Add route for API in api.php
- Test API. Can see all routes by command: $ php artisan route:list
> Firstly, create a new user if not exist then copy the token in response or log in by an existing user and copy the token.
>
> When accessing any API in which authentication is required, put token to the HTTP Header by set the value of the Authorization parameter with received token.
> 
>For ex. Authorization: Bearer {token here without {}}
