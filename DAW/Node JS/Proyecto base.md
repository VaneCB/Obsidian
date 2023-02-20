```bash
npm install -D prettier
```

Crear un fichero *.prettierrc.json* vacio (con dos llaves)
```bash
echo {}> .prettierrc.json
```

Instalar ***Prettier - Code formatter*** en Visual Studio Code

Añadie esto en el *package.json*:
```json
"devDependencies": {
	"prettier": "^2.8.4"
}
```

Sigue [[versionado semántico]]
¿Qué es versionado semántico? Forma de control de versiones para proyectos de software.

También se crea un package-lock.json con mis dependencias concretas.

Instalamos eslint y responderemos a las preguntas requeridas
```bash
npm init @eslint/config
```

Instalamos la integración de prettier con eslint
```bash
npm install --save-dev eslint-config-prettier
```

