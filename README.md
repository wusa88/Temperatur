# Temperatur

Image installieren:
2015-05-05-raspbian-wheezy.img

Raspi-Config
Change user password
Internationalisation Option
  Change Locale: de_DE.UTF-8 UTF-8
  Change Timezone
  Change Keyboard Layout - Classmate PC - Other - German
  Advanced Options - Device Tree
  
Expand Filesystem
Reboot


Aktualisieren:
sudo apt-get update
sudo apt-get upgrade


IP Adresse einstellen:
sudo nano /etc/network/interfaces


Swap deaktivieren:
sudo dphys-swapfile swapoff
sudo dphys-swapfile uninstall
sudo update-rc.d dphys-swapfile remove

Nginx installieren:
sudo apt-get install nginx php5-fpm php5-cgi php5-cli php5-common

Nginx anpassen:
root /var/www;

location ~ \.php$ {
	try_files $uri =404;
	fastcgi_split_path_info ^(.+\.php)(/.+)$;
	fastcgi_pass unix:/var/run/php5-fpm.sock;
	fastcgi_index index.php;
	include fastcgi_params;
}
 
# deny access to .htaccess files
location ~ /\.ht {
	deny all;
}

sudo nano /etc/nginx/sites-available/default
Zeile:
index index.html index.htm;
durch Zeile ersezten:
index index.html index.htm index.php;

Nginx Benutzer und Rechte:
sudo user add www-data
sudo group add www-data
sudo user mod –g www-data www-data
sudo mkdir /var/www
sudo chmod 775 /var/www –R
sudo chown www-data:www-data /var/www


Sqlite3 installieren
sudo apt-get install sqlite3


Dateien einfügen
