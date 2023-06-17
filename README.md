MySQL server Installation and  Set Up
======================================
* Step 1: Login to mysql instance and execute the below steps
```
sudo yum update -y && sudo yum install wget -y && sudo yum install git -y
```
* Step 2:Install MySQL server
```
curl -sSLO https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
md5sum mysql80-community-release-el7-5.noarch.rpm
sudo rpm -ivh mysql80-community-release-el7-5.noarch.rpm
sudo yum install mysql-server -y
sudo systemctl start mysqld
sudo grep 'temporary password' /var/log/mysqld.log
```
* Step 3: Secure MySQL server
```
sudo mysql_secure_installation
uncomment the below in vi /etc/my.cnf
default-authentication-plugin=mysql_native_password
```
* Step 4: Login to MySQL server
```
mysql -u root -p
```
* Step 5: create database with name indigo and user with name cloud
```
CREATE DATABASE indigo;
CREATE USER 'cloud'@'%' IDENTIFIED WITH mysql_native_password BY 'Cloud@123';
GRANT ALL ON *.* TO 'cloud'@'%';
FLUSH PRIVILEGES;
```
