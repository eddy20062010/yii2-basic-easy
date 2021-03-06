Yii 2 Basic Project Template with Easily
============================

Yii 2 Basic Project Template is a skeleton [Yii 2](http://www.yiiframework.com/) application best for
rapidly creating small projects.

The template contains the basic features including user login/logout, email system, RBAC, parsing and download excel file and a contact page.
It includes all commonly used configurations that would allow you to focus on adding new
features to your application.


DIRECTORY STRUCTURE
-------------------

      assets/             contains assets definition
      commands/           contains console commands (controllers)
      config/             contains application configurations
      controllers/        contains Web controller classes
      mail/               contains view files for e-mails
      models/             contains model classes
      runtime/            contains files generated during runtime
      tests/              contains various tests for the basic application
      vendor/             contains dependent 3rd-party packages
      views/              contains view files for the Web application
      web/uploads         contains excel file using parsing
      web/images/avatar   contains avatar users
      web/xls_parsing     contains the entry script and Web resources
      web/xls_sample      contains the entry script and Web resources



REQUIREMENTS
------------

The minimum requirement by this project template that your Web server supports PHP 5.4.0.


INSTALLATION
------------

### Install from an Archive File

composer require sintret/yii2-basic-easy

Set cookie validation key in `config/web.php` file to some random secret string:

```php
'request' => [
    // !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
    'cookieValidationKey' => '<secret random string goes here>',
],
```

You can then access the application through the following URL:

~~~
http://localhost/basic/web/
~~~


### Install via Composer

If you do not have [Composer](http://getcomposer.org/), you may install it by following the instructions
at [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix).

You can then install this project template using the following command:

~~~
composer global require "fxp/composer-asset-plugin:^1.2.0"
composer create-project --prefer-dist sintret/yii2-basic-easy basic
~~~

Now you should be able to access the application through the following URL, assuming `basic` is the directory
directly under the Web root.

~~~
http://localhost/basic/web/
~~~


CONFIGURATION
-------------

### Database

Edit the file `config/db.php` with real data, for example:

```php
return [
    'class' => 'yii\db\Connection',
    'dsn' => 'mysql:host=localhost;dbname=yii2basic',
    'username' => 'root',
    'password' => '1234',
    'charset' => 'utf8',
];
```

### Migration

Migration is simple inject your database using default data including for grid. You need open your console and then please follow code below 

```shell
yii migrate
```

### Go to your browser

Open your browser and go to your url for example "http://localhost/basic/web/". Username for default is "admin" and password "123456".

### RBAC

if you have done generate table using this generator "DIESEL CRUD Generator", you need checked each "ROLE" you defined.
Default Role in table "role" is "Admin" then add more role in mysql table role as you wish.
You can check/unchecked role at menu "Setting - Access Role" or "http://localhost/basic/web/role"

### Audit Trail

Audit Trail for a mysql table when you have defined fields in mysql table like "userCreate, userUpdate, createDate, updateDate".

### Image Processing

Default image proccessing using GD Library but you can change priority with optional gmacick or imagick in folder components SintretImagine class.
Default for mysql field name is "image".


**NOTES:**
- Yii won't create the database for you, this has to be done manually before you can access it.
- Check and edit the other files in the `config/` directory to customize your application as required.
- Refer to the README in the `tests` directory for information specific to basic application tests.
- Happy Coding
