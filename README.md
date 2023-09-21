# FIRSTNAME_Challange
AWS EC2 setup select Ubuntu 22 as OS and Firewall enable http and https port and launch the instance.
after setup connect and configure the ubuntu and install apache2 webserver.
$ sudo apt update
$ sudo apt install apache2 -y
Adjusting firewall setting in Apache2
$ sudo ufw app list
$ sudo ufw allow 'Apache'
$ sudo ufw status
Checking your Web Server
$ sudo systemctl status apache2
use your instance public ip address as host: my ip is 18.220.245.172 check this in web browser you will get default apache2 web page.

Setting Up Virtual Hosts
ibsar as my domain name

$ sudo mkdir /var/www/ibsar
$ sudo chown -R $USER:$USER /var/www/ibsar
$ sudo chmod -R 755 /var/www/ibsar
$ sudo nano /var/www/ibsar/index.html

nano editor open: copy hello world script in your nano editor and save it: Ctrl+O and Exit the editor Ctrl+X
HTML code:
<html> <head> <title>Hello World</title> </head> <body> <h1>Hello World!</h1> </body> </html>

In order for Apache to serve this content, it’s necessary to create a virtual host file with the correct directives. Instead of modifying the default configuration file located at /etc/apache2/sites-available/000-default.conf directly, let’s make a new one at /etc/apache2/sites-available/ibsar.conf:

$ sudo nano /etc/apache2/sites-available/ibsar.conf

nano editor open

<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName ibsar
    ServerAlias www.ibsar
    DocumentRoot /var/www/ibsar
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
Save the file Ctrl+O and Ctrl+X

Let’s enable the file with the a2ensite tool:

$ sudo a2ensite your_domain.conf
$ sudo a2dissite 000-default.conf
$ sudo apache2ctl configtest
$ sudo systemctl restart apache2

http://18.220.245.172   in web browser

END the task

