## Creación pareja clave pública y privada

Buscamos en home el fichero .ssh y creamos las claves
```bash
cd .ssh/
ssh -keygen
```

Llevamos la clave publica al servidor con el que me quiero conectar. Es importante la p en mayuscula. se indica la ruta del archivo y el servidor con su ruta donde queremos copiarlo.
```bash
cp -P22123 /home/alumno/.ssh/id_rsa.pub vanesa@54.37.220.7:/home/vanesa/.ssh/id_pub_insti.pub
```

Nos pedirá que nos identifiquemos en el servidor y ya lo copiará

Tenemos que tener un fichero authorized_keys. En ese fichero habra tantas claves publicas como conexiones tengamos. con el >> copiamos lo que tenemos en ese fichero dentro del otro fichero.

```bash
cat id_pub_insti.pub >> authorized_keys
```

## Creación de un alias

En local editamos nuestro fichero .bashrc
Con el comando source volvemos a cargar el fichero de configuración
Es importante que no haya espacio entre el = y lo escrito detrás
```bash
nano .bashrc
alias Vane="ssh -p22123 vanesa@54.37.220.7"
source .bashrc
Vane
```
Ahora simplemente poniendo Vane conectariamos al servidor

