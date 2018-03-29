# PHP Setup in Linux Mint

* ## **First update your system**

```
sudo apt-get update && apt-get upgrade -y
```

---

* ## **Install Apache2 Server**

```
sudo apt-get install apache2
```

Then open apache2 config file

```
sudo gedit /etc/apache2/apache2.conf
```

At the bottom of the file add this ip address

```
ServerName 127.0.0.1
```

Then restart the server

```
sudo systemctl restart apache2

```

After restart the server check if it set correct or not by using this command

```
sudo apache2ctl configtest
```

Then change the permission of the folder where php file are saved

```
sudo chmod 777 /var/www/html
```

---

* ## **Install Mysql Server**

```
sudo apt-get install mysql-server
```

---

* ## **Install Php**

```
sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql
```

Open apache config directory

```
sudo gedit /etc/apache2/mods-enabled/dir.conf
```

Delete index.php at the end of second line

Add index.php before index.html

Then restart the server

```
sudo systemctl restart apache2
```

---

* ## **Install PhpMyAdmin**

```
sudo apt-get install phpmyadmin
```

Open apache config folder

```
sudo gedit /etc/apache2/apache2.conf
```

At the bottom of file include

```
Include /etc/phpmyadmin/apache.conf
```

Then restart the server

```
sudo apachectl restart
```