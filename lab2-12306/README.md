# 数据库系统Lab2-12306

## 文件架构
```
SQL_lab2
├─php
│  ├─bin
│  │   ├─admin_signin
│  │   ├─user_signin
│  │   ├─user_signup
│  │   └─user_signup_random
│  ├─book
│  │   ├─book_admin
│  │   ├─book_back
│  │   ├─book_cancel
│  │   ├─book_confirm
│  │   ├─book_info
│  │   └─booking
│  ├─data
│  │   ├─station_data
│  │   └─train_data
│  ├─image
│  │   ├─ad
│  │   ├─background
│  │   ├─background
│  │   └─index-03
│  ├─search
│  │   ├─book_searc
│  │   ├─train
│  │   └─dist
│  ├─search
│  │   ├─book
│  │   ├─train_search
│  │   └─dist_search
│  ├─ign
│  │   ├─sign_admin
│  │   ├─sign_in
│  │   ├─sign_random
│  │   └─sign_up
│  ├─db
│  ├─index
│  └─test
└─README

```

## 使用说明

----------

* 环境：支持php和psql,装好驱动，通过localhost访问网页

* php与psql连接：

```php

   $connection_string = "host=localhost port=5432 dbname=lab2 user=root password=111111";

    $dbconn = pg_connect( $connection_string );

    if(! $dbconn )
    {
        exit('数据库连接失败！');
    }
    echo "<script>alert('哦豁，数据库连接成功！')</script>";
    
```

* psql建表语句
* 见db文件，逐段复制即可
* 启动环境webserv start
* 脚本如下：

```shell
#!/bin/bash

if [ "$1" != "" ]; then
   cmd="sudo service apache2 $1; sudo service postgresql $1"
   eval $cmd
else
   echo "No option was provided"
fi
```
* 将所有php中的文件拷贝到www/html文件目录下
* 最后在浏览器中输入localhost/index.php即可正常浏览
* ps：数据库连接成功会有弹窗提醒


## 具体功能

----------


1. 用户功能（注册、登录、游客）
2. 管理员功能（查看订单、用户）
3. 查询功能——包括两地间查询（含一次换乘）和具体车次查询
4. 订单功能——（包括余票连接预订和订单查看、订单取消功能）

