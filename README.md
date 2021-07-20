### Artisan Command

- php artisan make:controller PageController
- php artisan make:model Post -m
- php artisan make:model Post --migration
- php artisan migrate
- php artisan make:auth
- php artisan serve
- php artisan serve --port=3000
- php artisan make:middleware AuthWare
- php artisan make:seeder PostSeeder
- php artisan db:seed --class=PostSeeder
- php artisan db:seed
- php artisan migrate:reset 
- php artisan migrate
- php artisan migrate:fresh
- php artisan migrate:fresh --seed
- php artisan make:request PostRequest
- php artisan route:list
- php artisan make:resource PostResource
- php artisan tinker (laravel command line tool)

```
php artisan make:controller Backend/PostController -r
```

### Other Package

- composer require tymon/jwt-auth "1.*"
