# Guía de comandos para git

### Nuevo repositorio
Crea un repositorio nuevo 

`git init`

------------

### Clonar repositorio

Crea una copia local del repositorio ejecutando

`git clone /path/to/repository`

Para un servidor remoto, ejecuta

`git clone username@host:/path/to/repository`

Para clonar un repositorio de GitHub

`git clone https://...`

------------

### Añadir archivos y commit

Puedes registrar cambios (añadir al INDEX) usando

`git add NOMBRE_ARCHIVO`

`git add .`

Para hacer commit a estos cambios utiliza

`git commit -m "Mensaje del commit"`

Ahora el archivo (o archivos) están en el HEAD, pero no en tu repositorio remoto.

------------

### Status

Para ver el estado de tu actual espacio de trabajo tienes que utilizar el comando:

`git status`

------------

### Push

Tus cambios están ahora en el HEAD de tu copia local. Para enviar los cambios comiteados en el HEAD a tu repositorio remoto:

`git push origin master`

> Puedes cambiar la palabra 'master' por la rama a la que quieres enviar los cambios.

Es posible que el repositorio no haya sido clonado. Por ejemplo, cuando se ha creado desde cero. En ese caso si quieres conectar tu repositorio local a un repositorio remoto, utiliza:

`git remote add origin SERVIDOR_REMOTO`

------------

### Ramas

Crea una nueva rama con el nombre NOMBRE_RAMA y cámbiate a ella utilizando:

`git checkout -b  NOMBRE_RAMA`

Si necesitas volver a la rama master:

`git checkout master`

Para borrar la rama con nombre "nueva_rama" utiliza:

`git branch -d NOMBRE_RAMA`

La rama creada no estará subida al repositorio remoto hasta que no hagas push con este comando:

`git push origin NOMBRE_RAMA`


------------

### Pull y merge

Para actualizar tu repositorio local al último commit, hazlo con el comando:

`git pull`

> Este comando fusiona tu espacio de trabajo con el último commit remoto

Para fusionar tu espacio de trabajo con una rama en concreto, utiliza

`git merge NOMBRE_RAMA`

Git intentará hacer estos comandos automáticos, pero no siempre puede. A veces aparecen conflictos. Estos conflictos hay que resolverlos manualmente y después deberás añadirlos mediante:

`git add NOMBRE_ARCHIVO`

Si necesitas comopar dos ramas, utiliza:

`git diff NOMBRE_RAMA1 NOMBRE_RAMA2`

------------

### Tags

Es recomendable crear etiquetas para cada versión del producto final.

Para esto, utiliza:

`git tag 1.0.0 xxxxxxxxxx`

Donde xxxxxxxxxx es el ID del commit al que quieres hacer mención.
Este id lo puedes sacar mediante 

`git log`

o mirando en el repositorio remoto si utilizas GitHub, GitLab...

------------

### Cambios locales (por si algo sale mal)

Con

`git checkout -- NOMBRE_ARCHIVO`

se cambian el archivo en tu espacio de trabajo con el último contenido del HEAD. Los cambios que ya han sido agregados al INDEX, y los nuevos archivos permanecerán sin cambio.

Si lo que necesitas es revertir todos los cambios locales y commits, puedes traer la última versión remota con:

`git fetch origin`

`git reset --hard origin/master`

> El git reset no es lo más recomendable pero como último recurso está bien.

 

###End
