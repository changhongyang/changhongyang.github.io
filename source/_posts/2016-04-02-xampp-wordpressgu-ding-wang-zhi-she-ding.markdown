---
layout: post
title: "XAMPP Wordpress固定網址設定"
date: 2016-04-02 23:53:38 +0800
comments: true
categories: XAMPP
---
* 1.修改/Applications/XAMPP/xamppfiles/etc/httpd.conf

1-1. 尋找

<!--more-->
```
LoadModule rewrite_module modules/mod_rewrite.so
```
確認前面沒有#字號

1-2. 將 AllowOverride None 改為 AllowOverride All
```
<Directory />   
Options FollowSymLinks   
AllowOverride None   
</Directory>
```
1-3. 重新啟動XAMPP

* 2.修改或新增.htaccess檔案
```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /wordpress/
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /wordpress/index.php [L]
</IfModule>
```
