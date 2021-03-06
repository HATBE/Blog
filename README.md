# Feautures

- Markdown Support
- User Management
- Installer
# Installation

Base OS: Ubuntu-server 20.04

## LAMP

``` bash
$ sudo apt update
```

As the Webserver, a Apache2 is used.

``` bash
$ sudo apt install apache2
```

As the Database server, a MariaDB is used.

``` bash
$ sudo apt install mariadb-server
$ mysql_secure_instalation
Change the root password? [Y/n] n
Remove anonymous users? [Y/n] y
Disallow root login remotely? [Y/n] y
Remove test database and access to it? [Y/n] y
Reload privilege tables now? [Y/n] y
```  

PHP Installation.

``` bash
$ sudo apt install php libapache2-mod-php php-gmp php-curl php-gd php-mysql php-mbstring php-initl php-bcmath php-imagick php-xml php-zip
```

Now we can prepare the System.

``` bash
$ sudo chown www-data:www-data /var/www/html
$ sudo systemctl reload apache2
```

## Install the Blog

Create the Database.

``` bash
$ sudo mysql -u root -p
```

``` SQL
CREATE DATABASE blog;
CREATE USER bloguser IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON blog.* TO bloguser;
EXIT;
```

``` bash
$ cd /var/www/html
$ git clone https://github.com/HATBE/Blog.git .
$ sudo chmod 755 /var/www/html -R
$ sudo chown www-data:www-data /var/www/html
```

Now, you can navigate to https://<ip/host> in your browser.

Follow the instructions of the installer.

Standard credentials:
Username: admin
Password: 1234
