MySQL server Installation and  Set Up
======================================
* Step 1: Login to mysql instance and execute the below steps
sudo yum update -y && sudo yum install wget -y && sudo yum install git -y

* Step 2:Install MySQL server
sudo wget https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm
sudo rpm -Uvh mysql80-community-release-el7-1.noarch.rpm
sudo yum install mysql-server -y
sudo systemctl start mysqld
sudo grep 'temporary password' /var/log/mysqld.log

* Step 3: Secure MySQL server 
sudo mysql_secure_installation

* Step 4: Login to MySQL server
mysql -u root -p

* Step 5: create database with name indigo and user with name cloud 
mysql>create database indigo;
mysql>CREATE USER 'cloud'@'%' IDENTIFIED BY 'Cloud@123';
mysql>GRANT ALL ON *.* TO 'cloud'@'%';
mysql>FLUSH PRIVILEGES;
