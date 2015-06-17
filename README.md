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


IP Adresse einstellen:
sudo nano /etc/network/interfaces


Swap deaktivieren:
sudo dphys-swapfile swapoff
sudo dphys-swapfile uninstall
sudo update-rc.d dphys-swapfile remove

Nginx installieren:
sudo apt-get install nginx

Nginx anpassen:
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

