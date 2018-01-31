# PHP_Laravel_Mysql_Crud

1. set up wamp server

2. put lsapp in WWW of wamp_server

3. in C:\wamp64\bin\apache\apache2.4.23\conf\extra

edit  file: httpd-vhosts.conf to add:

####################################

<VirtualHost *:80>
	ServerName lsapp
	DocumentRoot c:/wamp64/www/lsapp/public	
<Directory  "c:/wamp64/www/">
		Options +Indexes +Includes +FollowSymLinks +MultiViews
		AllowOverride All
		Require local
	</Directory>
</VirtualHost>

##########################################

4. in C:\Windows\System32\drivers\etc

edit file host to add:

##########################

127.0.0.1 lsapp

##########################

5. config Mysql

Please note some important usage for Laravel:

$ php artisan make:controller PagesController

npm install

npm run dev

npm run watch

# add own CSS in file:
lsapp/resources/assets/sass/_custom.scss

in lsapp/resources/assets/sass/app.scss add:

@import "custom";

$ php artisan make:controller Postcontroller

$ php artisan make:controller Postcontroller --resource
#makePostmodel with migration posibility:
$ php artisan make:model Post -m
#From model to databese table:
$ php artisan migrate

.......................................
表中插入数据:
$ php artisan tinker

>>> App\Post::count()

>>> $post =new App\Post();

>>> $post->title='Postone';

>>> $post->body='This is the post body!';

>>> $post->save();
..................................................................
$ php artisan route:list


------------------------------------------------------------------

https://laravelcollective.com/docs/5.4/html

composer require "laravelcollective/html":"^5.4.0"

------------------------------------------------------------------


$ composer require unisharp/laravel-ckeditor

$ php artisan vendor:publish --tag=ckeditor

-------------------------------------------------------------------
$ php artisan make:auth   //自动产生login注册页面

$ php artisan make:migration add_user_id_to_posts    //然后到migrations去修改文件

$ php artisan migrate

$ php artisan make:migration add_cover_image_to_posts  //然后到migrations去修改文件

$ php artisan migrate
----------------------------------------------------------------------------

$ php artisan storage:link     //The [public/storage] directory has been linked.外部可以访问storage！！！
