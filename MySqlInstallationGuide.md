## Instructions


Install MySQL and start it using the following commands


```sh
sudo rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2023
sudo yum install -y https://dev.mysql.com/get/mysql80-community-release-el7-3.noarch.rpm
sudo amazon-linux-extras install epel -y
sudo yum install -y mysql-community-server

sudo systemctl start mysqld 
sudo systemctl enable mysqld 
```


Get the password for the root user:


```sh
sudo grep 'temporary password' /var/log/mysqld.log
```


Login to MySQL:


```sh
mysql -u root -p
```


You have to change the root user's password before you can do anything, so run the following command to do that:


```mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Rajan@2024';
```



Create a new user called `rajan` with the password `Rajan@2024` that can access the database from localhost:


```mysql
CREATE USER 'rajan'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Rajan@2024';
GRANT ALL PRIVILEGES ON *.* TO 'rajan'@'localhost';
```


Now, we're good to start with MySql.

```mysql
mysql -u root -p

or

mysql -u root -h hostname||ip -p
```

Verify the MySql version
```mysql

mysql --version

```
```mysql

```mysql
start or stop mysql

sudo systemctl start mysqld
sudo systemctl enable mysqld 
```
