[[Crear credenciales https]]

Lo descargamos

```bash
curl -O [https://releases.wikimedia.org/mediawiki/1.37/mediawiki-core-1.37.6.tar.gz](https://releases.wikimedia.org/mediawiki/1.37/mediawiki-core-1.37.6.tar.gz)
```

Lo descomprimimos

```bash
sudo tar -xf mediawiki-core-1.37.6.tar.gz
```

Lo pasamos a nuestra carpeta miwiki

```bash
sudo mv mediawiki-1.37.6 miwiki
```

Le damos los permisos y cambiamos el usuario de miwiki

```bash
sudo chown -R www-data:www-data miwiki
sudo chmod -R 775 miwiki
```

Instalamos lo necesario
```bash
sudo apt-get install php-apcu php-intl php-mbstring php-xml php-mysql php-calendar
sudo systemctl reload apache2
```

Se descargara a la maquina fisica un archivo LocalSettings.php que habra que mover a la maquina virtual.
Desde tu maquina fisica

```bash
sudo scp LocalSettings.php alumno@172.30.1.183:/home/alumno
```

En la maquina virtual copiamos el archivo a la carpeta miwiki y le damos otra vez usuario y permisos:

```bash
sudo mv LocalSettings.php /var/www/miwiki/
sudo chown -R www-data:www-data /var/www/miwiki
sudo chmod -R 775 /var/www/miwiki
```
