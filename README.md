database migration
==================
yii2 database migration ,it is easy!

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist xiaochengfu/yii2-migrate "*"
```

or add

```
"xiaochengfu/yii2-migrate": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```
网页端使用:

1.在 backend/config/main.php 添加如下配置

'modules' => [
        'migration' => [
            'class' => 'xiaochengfu\migrate\Module',
        ]
    ],
```
2.在你的后台访问 http://yourdomain/migration

演示地址： http://yii.phpsy.cn/migration



命令行使用方法:

1.在`console/config/main.php` 添加如下配置
```
'controllerMap' => [
        'migrate' => [
                    'class' => 'xiaochengfu\migrate\console\MigrateController',
                    'useTablePrefix' => true,
                    'migrationPath' => '@console/migrations',
                ],
    ],
```

2.将迁移文件转存,及备份
`php yii migrate/dump`

3.还原指定文件
`php yii migrate/to m170420_151515_migration.php`

```