# ROUTE 53 HANDS-ON

### Installation Script (Region-1)

```sh
#!/bin/bash
sudo yum update -y
sudo yum install git httpd -y
sudo service httpd start
sudo chkconfig httpd on
git clone https://github.com/pandacloud1/webapp1.git && cd webapp1
sudo cp * -R /var/www/html/
```

### Installation Script (Region-2)

```sh
#!/bin/bash
sudo yum update -y
sudo yum install git httpd -y
sudo service httpd start
sudo chkconfig httpd on
git clone https://github.com/pandacloud1/webapp1-india.git && cd webapp1-india
sudo cp * -R /var/www/html/
```
