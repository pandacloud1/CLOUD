## WEBSERVER & DATABASE SERVER SCRIPTS

### WEBSERVER SCRIPT (Add inside custom data)
```sh
#!/bin/bash
apt update -y
apt install apache2 git -y
git clone https://github.com/pandacloud1/webapp1.git && cd webapp1
cp * -R /var/www/html/
```

### DATABASE SERVER SCRIPT (SSH login)
```sh
# Installing MySQL Client
#!/bin/bash
sudo apt update
sudo apt install mysql-client -y
mysql --version

# Installing MySQL Server
sudo apt install mysql-server -y
sudo systemctl start mysql
sudo systemctl enable mysql
systemctl status mysql

sudo mysql

# Set New Root Password
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'P@$$worD';
FLUSH PRIVILEGES;
EXIT;

# Login with New Password
mysql -u root -p
```

## ADDING ENTRIES IN DATABASE
### Clear the screen
```sh
system clear;
```

### Create a new database, switch to the newly created database, create table & add entries
```sh
CREATE DATABASE my_database;
USE my_database;
CREATE TABLE mytable (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    mobile_no VARCHAR(15) NOT NULL,
    email VARCHAR(255) NOT NULL
);
INSERT INTO mytable (name, mobile_no, email) VALUES ('alex', '9876543210', 'alex@example.com');
INSERT INTO mytable (name, mobile_no, email) VALUES ('charlie', '9876543220', 'charlie@example.com');
INSERT INTO mytable (name, mobile_no, email) VALUES ('ethan', '9876543230', 'ethan@example.com');
```

### View the table
```sh
SELECT * FROM mytable;
```
<img width="723" height="180" alt="image" src="https://github.com/user-attachments/assets/42c0a1a9-4201-4593-a426-27688c40556a" />
