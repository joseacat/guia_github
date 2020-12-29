## Guía de comandos para git

### Nuevo repositorio
Crear un repositorio nuevo 

`git init`

### Clonar repositorio
Crea una copia local del repositorio ejecutando

`git clone /path/to/repository`

Para un servidor remoto, ejecuta

`git clone username@host:/path/to/repository`

Para clonar un repositorio de GitHub

`git clone https://...`

### Añadir archivos y commit

Puedes registrar cambios (añadir al INDEX) usando

`git add NOMBRE_ARCHIVO`

`git add .`

Para hacer commit a estos cambios utiliza

`git commit -m "Mensaje del commit"`

Ahora el archivo (o archivos) están en el HEAD, pero no en tu repositorio remoto.

### Push

Tus cambios están ahora en el HEAD de tu copia local. Para enviar los cambios comiteados en el HEAD a tu repositorio remoto:

`git push origin master`

> Puedes cambiar la palabra 'master' por la rama a la que quieres enviar los cambios.

Es posible que el repositorio no haya sido clonado. Por ejemplo, cuando se ha creado desde cero. En ese caso si quieres conectar tu repositorio local a un repositorio remoto, utiliza:

`git remote add origin SERVIDOR_REMOTO`

### Ramas
