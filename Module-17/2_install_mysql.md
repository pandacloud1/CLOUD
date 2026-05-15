## INSTALLING MYSQL IN AMAZON LINUX 2023
- REF: [https://dev.to/aws-builders/installing-mysql-on-amazon-linux-2023-1512]

### Installing mysql client
```sh
#!/bin/bash
sudo wget https://dev.mysql.com/get/mysql80-community-release-el9-1.noarch.rpm
sudo dnf install mysql80-community-release-el9-1.noarch.rpm -y
sudo rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2023
sudo dnf install mysql-community-client -y
mysql --version
```
### Installing mysql server
```
sudo dnf install mysql-community-server -y
sudo systemctl start mysqld
sudo systemctl enable mysqld
systemctl status mysqld
```

### Get Temporary Root Password
```sh
sudo grep 'temporary password' /var/log/mysqld.log
```

### Login & set new password
```sh
mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED BY '<New password>';
FLUSH PRIVILEGES;
```
