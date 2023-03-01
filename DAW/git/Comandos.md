
## Sin ssh

Si no queremos conectar con ssh ya NO podemos autenticar con usuario y password, tendremos que crear un **TOKEN** que funcionará a modo de password. Lo configuramos en *github* en *setting* -> *develop setting* -> token clasico -> configuramos tiempo de acceso y que tiene permitido hacer.
***

### 1. Creamos el repositorio en github

### 2. En nuestro ordenador vamos a la carpeta de nuestro proyecto

Primero iniciamos git
```bash
git init
```
se crea la carpeta oculta .git donde podemos mantener control sobre el proyecto

Para cambiar el nombre de la rama master a rama main para que no haya conflicto con github
```bash
git branch -m main
```

Después realizamos un commit en el que ponemos un comentario sobre lo que vamos a subir:
```bash
git commit -m "tu comentario"
```

Si hemos modificado un fichero y no queremos hacer un commit especifico para él, lo haremos de la siguiente manera
```bash
git commit -a
```
Añadimos los ficheros o carpetas que queremos subir al repositorio:
```bash
git add -A
git add *
```
con el -A añadimos todos los archivos, si solo fueran archivos concretos *git add nombrearchivo*

Para comprobar lo que esta listo para hacer push, o en general para ver la situación ficheros sin seguimiento, ficheros en el commit,etc
```bash
git status
```

Si queremos sacar algun archivo del commit o stage area:
```bash
git rm --cached *nombrearchivo*
```

Para sacar un archivo del area de Stage
```bash
git restore --staged <archivo>
```

Indicamos el repositorio de github donde vamos a subir
```bash
git remote add origin *url del repositorio del github*
```

Subimos los archivos a nuestro repositorio en github (la u solo para la primera vez)
```bash
git push -u origin master(o main)
```


### 3. Para clonar un repositorio a nuestro ordenador
```bash
git clone *url del repositorio*
```

Podemos primero clonar el proyecto y entonces ya no necesitariamos al hacer **push** el repositorio al que vamos a subir

### 4. Realizar un Pull

Nos descargamos del repositorio las actualizaciones que ha sufrido el mismo
```bash
git pull
```

Si tenemos fallo en el git pull por conflicto de actualización de ficheros podemos usar lo siguiente:

- Un commit previo nosotros para tener "marcha atras"
- Utilizamos el siguiente código para mergear:
```bash
git config pull.rebase false
```

o bien desplazarte entre las ramas creadas por git branch si tenemos problemas con las ramas
```bash
git checkout --theirs *ruta del fichero*
```

### 5. El uso de las ramas

Creamos una nueva rama
```bash
git branch develop
```

Si queremos ver las ramas que tenemos
```bash
git branch
```

Para cambiar de una rama a otra
```bash
git checkout develop
```

### 6. Mergear ramas


Las fusiones se hacen poniendose en la rama donde quiero hacer la fusion (donde quiero llevar el flujo me pongo)

```bash
git checkout develop
git merge feature1
```

Al hacer el merge indicamos que rama es la que queremos fusionar

Una vez hemos hecho esto y que estan fucionadas en local hacemos un
```bash
git push origin develop
```
