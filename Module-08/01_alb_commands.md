## USER DATA COMMANDS FOR EC2 USING LOAD BALANCER

COMMANDS FOR AMAZON LINUX
```sh
#!/bin/bash									
sudo su -								
sudo yum update -y									
sudo yum install httpd -y								
sudo service httpd start							
chkconfig httpd on							
sudo echo "WELCOME TO SERVER NO. $(hostname -i)" > /var/www/html/index.html
```

COMMANDS FOR UBUNTU
REF: [https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-22-04]
```sh
#!/bin/bash									
sudo su -									
apt update -y
apt install apache2 -y
service apache2 start
echo "WELCOME TO SERVER NO. $(hostname -i)" > /var/www/html/index.html
```
