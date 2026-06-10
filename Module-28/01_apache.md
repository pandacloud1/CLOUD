## INSTALLING APACHE IN UBUNTU 
REF: [https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-22-04]

```sh
#!/bin/bash
sudo su -
apt update
apt install apache2 -y
systemctl status apache2
echo "THIS IS MY FIRST SERVER" > /var/www/html/index.html
```
