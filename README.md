# Chevereto-Free-Multi-Language

Chevereto-Free允许你在你自己的服务器上创建一个全功能的多语言图像托管网站。这是你的主机和你的规则，告别关闭和限制。

> 另一个 chevereto中文 Fork -> [CheveretoChina 基于 Chevereto-Free 开发的图床程序](https://hostloc.com/thread-980212-1-1.html)

## 🦓 关于本 fork

Chevereto-Free-Multi-Language 是 [Chevereto-Free](https://github.com/rodber/chevereto-free/)的一个Fork，其中只保留了基本的功能。Chevereto-Free适用于个人使用和小型社区。

👉 **本fork相比源fork的变化**

* 撤销 "删除多语言支持"
* 撤销 "删除审定"
* 撤销 "删除批量导入内容"

## 🧐 需求

* PHP 7.2
* MySQL 5.7 / 8 - MariaDB 10
* Apache HTTP Web Server
  * mod_rewrite

## 操作处理
1、权限
```java
chmod -R 777 app
chmod -R 777 content
chmod -R 777 images
```

2、伪静态
```java
location / {
    if (-f $request_filename/index.html){ rewrite (.*) $1/index.html break; } if (-f $request_filename/index.php){ rewrite (.*) $1/index.php; } if (!-f $request_filename){ rewrite (.*) /index.php; } try_files $uri $uri/ /api.php; } location /admin { try_files $uri /admin/index.php?$args;
    }
```

3、安装后切换中文
在安装界面填的那个数据库里找到chv_users，在这个里面找到你登录的账户，将user_language字段改为zh-CN，再刷新图床页面，即可看到界面变为中文

## 📚 文档

[chevereto-free.github.io](https://chevereto-free.github.io)  
[如何安装 && 切换中文](https://github.com/keven1024/chevereto-free-multi-language/discussions/1)  
[CSDN:宝塔chevereto1.6.2中文最新版踩坑教程](https://blog.csdn.net/qq_38862981/article/details/123142148)

