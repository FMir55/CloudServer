# Set Up Apache Virtual Hosts on Ubuntu
###Create the Directory Structure
```
sudo mkdir -p /var/www/example.com/shop1
sudo mkdir -p /var/www/example2.com/shop2
```
###Grant Permissions
```
sudo chown -R $USER:$USER /var/www/example.com/shop1
sudo chown -R $USER:$USER /var/www/example2.com/shop2
sudo chmod -R 755 /var/www
```
###Create Demo Pages for Each Virtual Host
```
nano /var/www/shop1/index.html
nano /var/www/shop2/index.html
```
###Create New Virtual Host Files
#####Create the First Virtual Host File
```
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/example.com.conf
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/example2.com.conf
sudo nano /etc/apache2/sites-available/example.com.conf
```
```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/example.com/shop1
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```