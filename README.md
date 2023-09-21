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




Managing the Apache Process
$ sudo systemctl stop apache2



