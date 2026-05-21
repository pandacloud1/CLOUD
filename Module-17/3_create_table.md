## ADDING ENTRIES IN DATABASE
### Clear the screen
```sh
system clear;
```

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
