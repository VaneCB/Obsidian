Con el siguiente comando generamos la credenciales, nos pedirá configurarlas:
```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
```

- Country Name (2 letter code) [AU]:ES
- State or Province Name (full name) [Some-State]:Zaragoza
- Locality Name (eg, city) :Zaragoza
- Organization Name (eg, company) [Internet Widgits Pty Ltd]:inaem
- Organizational Unit Name (eg, section) :Desarrolladores
- Common Name (e.g. server FQDN or YOUR name) :alumno
- Email Address :admin@inaem.org

Entramos al archivo de configuracion de ssl:
```bash
sudo nano /etc/apache2/sites-available/default-ssl.conf
```
 Cambiamos los que hay por los que hemos generado:
 SSLCertificateFile      /etc/ssl/certs/apache-selfsigned.crt
 SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key

Configuramos apache
 ```bash
 sudo a2enmod ssl
 sudo a2enmod headers
 sudo a2ensite default-ssl.conf
 sudo apache2ctl configtest
 sudo systemctl reload apache2
 ``` 
```bash
etc/apache2/sites-available$ sudo nano miwiki.com.conf
sudo cp default-ssl.conf miwiki.com.conf
sudo nano miwiki.com.conf 
```

En nuestra maquina fisica

- Vamos a sudo nano /etc/hosts
Añadimos ahí la direccion de la maquina virtual con los sitios:
- 172.30.1.183 www.miwiki.com
- 172.30.1.183 miwiki.com

Volvemos a nuestra maquina virtual:

```bash
sudo a2ensite miwiki.com.conf
systemctl reload apache2
```

Vamos a instalar Mediawiki [[MEDIAWIKI]]