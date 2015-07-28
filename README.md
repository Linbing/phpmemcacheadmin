# phpmemcacheadmin
Automatically exported from code.google.com/p/phpmemcacheadmin
1、git clone git@github.com:Linbing/phpmemcacheadmin.git

2、mv  phpmemcacheadmin /var/www/phpMemcachedAdmin

3、cd /var/www & chown -R apache.apache phpMemcachedAdmin & chmod -R 755 phpMemcachedAdmin

4、 vim /etc/httpd/conf.d/phpMemcachedAdmin.conf

Alias /phpMemcachedAdmin /var/www/phpMemcachedAdmin
Alias /phpmemcachedadmin /var/www/phpMemcachedAdmin

<Directory /var/www/phpMemcachedAdmin>
     Order Deny,Allow
     Deny from All
     Allow from192.168.1.0/24Allow from127.0.0.1</Directory>
<Directory /var/www/phpMemcachedAdmin>
     AuthUserFile /etc/httpd/.htpasswd
     AuthName "phpMemcachedAdmin Login Area"
     AuthType Basic
     require useradmin</Directory>
     
5、htpasswd -cm/etc/httpd/.htpasswdadmin

New password:
Re-type new password:
Adding password for user admin

6、service httpd restart

7、access：127.0.0.1:80/phpMemcachedAdmin



