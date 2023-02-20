Con phpstorm y con visual studio code

## Con phpstorm

Tools -> deployment -> browse remote host -> añadimos nuevo servidor y lo configuramos
alt+mayus+Q para guardar y subir cambios al servidor

El docker-compose añadiendo mysql y phpmyadmin

version: '3'

services:
  web:
    image: nginx
    container_name: "web-manuel"
    restart: always
    environment:
      - LETSENCRYPT_HOST=manuel.certweb.infenlaces.com
      - LETSENCRYPT_EMAIL=nombre@mail.com
      - VIRTUAL_HOST=manuel.certweb.infenlaces.com
    volumes:
      - ./nginx/default.conf:/etc/nginx/conf.d/default.conf:ro
      - ./sitiophp:/usr/share/nginx/html
    networks:
      - nginx-proxy_frontend
      - backend

  php:
    image: php:fpm
    volumes:
      - ./sitiophp:/usr/share/nginx/html
    logging:
      driver: "json-file"
      options:
        max-size: "200m"
        max-file: "5"
    networks:
      - backend

  mysql:
    image: docker.io/bitnami/mysql:latest
    container_name: "manuel-mysql"
    environment:
      # ALLOW_EMPTY_PASSWORD is recommended only for development.
      - ALLOW_EMPTY_PASSWORD=yes
      - MYSQL_USER=manuel
      - MYSQL_PASSWORD=manuel
      - MYSQL_DATABASE=roles

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    ports:
      - 8800:80
    depends_on:
      - mysql
    environment:
      - PMA_ARBITRARY=1
      - PMA_HOST=mysql

networks:
  nginx-proxy_frontend:
    external: true
  backend:
    driver: bridge