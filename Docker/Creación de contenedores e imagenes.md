## Docker run

Crear un contenedor a partir de una imagen:
```bash
docker run --name nombre_contenedor -t -i -p 8800:80 -v /home/usuario/dir_maquina_local:/var/www/html ubuntu:latest
```

Crear una imagen a partir de un contenedor (cuidado los volumenes compartidos no se copian):

```bash
docker commit -m "mensaje" -a "autor" contenedor nombre_imagen_que_creo:tag
```

Mapear los puertos( establecer un fordward)
```bash
docker run --name web -p 8880:80
docker run --name web -p 8880-8810:80
```

Vamos a tener un directorio compartido. Manda el anftrion. Todo lo que haa y creemos en el contendor estará disponible en el anfitrión.
```bash
docker run --name web -p 8080:80 -v /home/alumno/docker:/var/www/html
```

Se abrira el contenedor en una maquina:
```bash
docker run -t -i --name web -p 8080:80 -v /home/alumno/docker:/var/www/html 
```

MIrar las imagenes que hay y su estado
```bash
docker ps -a
```

docker commit -m "contenedor con apache" web

## Docker-compose:

Creo cada contener con un servicio
dockerfile utiliza el servicio de identacion de *Python*

```bash
docker 
```


Creamos el yml donde vamos a configurar
```bash
nano docker-compose.yml
```
En el directorio donde esta el fichero yml ponemos:
```bash
docker compose up -d
```

Para eliminar el contenedor:
```bash
cocker compose down
```
Va a mostrar lo que vamos haciendo:
```bash
docker compose logs -f
```
