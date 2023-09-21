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
