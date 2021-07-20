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

### Git 

git init
git add .
git commit -m "sample crud"
git remote add origin https://github.com/bm-member/bm-blog-2.git
git push -u origin master


### Todo
- search
- image upload
- factory
- login with username
- role and permission
- localization
- email verify
- api
- api auth
- api resouce
- sql query join

---

   <div class="form-group">
        <label>Profile Image</label>
        <input type="file" class="form-control-file" name="image">
    </div>
---
    $table->string('image')->nullable();
----

sidebar(layout/sidebar)

    @if(auth()->user()->image)
        <img src="{{ asset( 'upload/profile/' . auth()->user()->image) }}" class="img-circle elevation-2"
            alt="User Image">
    @endif

--- <img src="{{ asset( 'upload/profile/' .$shop->image) }}"
conrtoller

    
    if($request->hasFile('image')) {
        $img = $request->file('image');
        $folder = public_path('upload/profile/');
        $imgName = time() . '.' . $img->getClientOriginalExtension();
        $img->move($folder, $imgName);
        $old_folder=$folder.$user->image;
        if(file_exists($old_folder)){
            @unlink($old_folder);
        }
        $user->image = $imgName;
    }

    if($request->password !== null) {
        $user->password = bcrypt($request->password);
    }
    $user->save();

---
categories (name)
	
	- categories_shop ( category_id,shop_id )

	- belongsToManyy(Shop::class)

shop 	(name, description,address,latitude, longitude, image, active)
	
	- day_shop( day_id, shop_id, from_hours, from_minutes, to_hours, to_minutes )

	- belongsToMany(Category::class)
	- belongsToMany(Day::class)

day (name)

	- no

One to Many 
~~~~~~~~~~~
User
    - hasMany(Shop::class, 'created_by_id', 'id');

Shop
    - belongsTo(User::class, 'created_by_id');


git init
git add .
<IfModule mod_rewrite.c>
    <IfModule mod_negotiation.c>
        Options -MultiViews -Indexes
    </IfModule>

    RewriteEngine On

    # Handle Authorization Header
    RewriteCond %{HTTP:Authorization} .
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]

    # Redirect Trailing Slashes If Not A Folder...
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_URI} (.+)/$
    RewriteRule ^ %1 [L,R=301]

    # Handle Front Controller...
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [L]
</IfModule>

Passport
php artisan passport:install
1HNVK9nJit4FzeEuHsFamFj5CIxwty4ZSEusnZLK

http://localhost:8000/oauth/token

grant_type  passport or client_credentials
client_id   6
client_secret   ---
username    admin@gmail.com
password    password
scope   *


/api/v1/categories
Authorization => Bearer Token 

#Heroku
# # # # #
heroku login

web: vendor/bin/heroku-php-apache2 public/

heroku create
git remote -v
git push heroku master

setting=> debug,key
heroku config:add APP_NAME=Laravel
heroku config:add APP_ENV=production
heroku config:add APP_URL=https://quiet-caverns-43354.herokuapp.com/
Setting-> heroku postgres
heroku pg:credentials:url

heroku config:add DB_CONNECTION=pgsql
heroku config:add DB_HOST=ec2-35-170-85-206.compute-1.amazonaws.com
heroku config:add DB_PORT=5432
heroku config:add DB_DATABASE=d65mg9p2bhuc74
heroku config:add DB_USERNAME=qbzdkpghngflpk
heroku config:add DB_PASSWORD=ca095cec1547b80b804df33d609255f33-1.amazonaws.com
heroku config:add GOOGLE_MAPS_API_KEY=AIzaSyAAerhW43ec_f96kLaglZpXbC6S_9TZYzk

heroku run
heroku run php artisan migrate
php artisan make:auth
git status

"dbname=d65mg9p2bhuc74 
host=ec2-35-170-85-206.compute-1.amazonaws.com 
port=5432 
user=qbzdkpghngflpk 
password=ca095cec1547b80b804df33d609255f33-1.amazonaws.com 
port=5432 
user=qbzdkpghngflpk 
password=ca095cec1547b80b804df33d609255f331373d9e6a756ecd352fb7de874e239f sslmode=require"