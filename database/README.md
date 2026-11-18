# Database – MariaDB Setup (Ubuntu)

This guide explains how to install MariaDB, create the database and table, and create a database user for the backend.

## 1. Install MariaDB
```bash
sudo apt update && sudo apt install mariadb-server -y
```

## 2. Secure MariaDB
```bash
sudo mysql_secure_installation
```
Follow the prompts to:
- Set a root password
- Remove anonymous users and the test database
- Disable remote root login

## 3. Create the database and user
Log in:
```bash
sudo mysql -u root -p
```
Run:
```sql
CREATE DATABASE student_db;
CREATE USER 'student_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON student_db.* TO 'student_user'@'localhost';
FLUSH PRIVILEGES;
```
Replace `student_user` and `your_password` with your own values.

> If the backend runs on a **different server**, use `'student_user'@'<BACKEND_PRIVATE_IP>'` instead of `localhost`, and set `bind-address` in the MariaDB config so it accepts that connection.

## 4. Create the table
```sql
USE student_db;
```
Then run [schema.sql](schema.sql), or from the terminal:
```bash
sudo mysql -u root -p < schema.sql
```

## 5. Credentials needed by the backend
| Variable | Meaning |
|----------|---------|
| DB_HOST | Database server IP or hostname |
| DB_PORT | 3306 |
| DB_NAME | student_db |
| DB_USER | student_user |
| DB_PASS | your password |

## 6. Verify
```sql
SHOW TABLES;
DESCRIBE students;
```
Take a screenshot of this output for your project documentation.
