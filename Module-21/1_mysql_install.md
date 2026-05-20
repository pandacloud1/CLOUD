## INSTALLING MYSQL IN AMAZON LINUX 2023
- REF: [https://dev.to/aws-builders/installing-mysql-on-amazon-linux-2023-1512]

### Installing mysql client
- No need to install mysql server package as we are using RDS 
```sh
#!/bin/bash
sudo wget https://dev.mysql.com/get/mysql80-community-release-el9-1.noarch.rpm
sudo dnf install mysql80-community-release-el9-1.noarch.rpm -y
sudo rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2023
sudo dnf install mysql-community-client -y
mysql --version
```

### Command to access RDS through Bastion
```sh
mysql -h <RDS-endpoint> -u admin –p 
# Hit 'Enter' & enter your password
```

## ADDING ENTRIES IN DATABASE

### Create a new database
```sh
CREATE DATABASE my_database;
```

### Switch to the newly created database
```sh
USE my_database;
```

### Create a table
```sh
CREATE TABLE mytable (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    mobile_no VARCHAR(15) NOT NULL,
    email VARCHAR(255) NOT NULL
);
```

### Insert values in the table
```sh
INSERT INTO mytable (name, mobile_no, email) VALUES ('alex', '9876543210', 'alex@example.com');
INSERT INTO mytable (name, mobile_no, email) VALUES ('charlie', '9876543220', 'charlie@example.com');
INSERT INTO mytable (name, mobile_no, email) VALUES ('ethan', '9876543230', 'ethan@example.com');
```

### View the table
```sh
SELECT * FROM mytable;
```
<img width="723" height="180" alt="image" src="https://github.com/user-attachments/assets/42c0a1a9-4201-4593-a426-27688c40556a" />
