# Uso básico de Git y Github

Este es el primer ejercicio del curso de Udemy _Git & Github Crash Course: Create a Repository From Scratch!_ del Kalob Taulien

.md -> [Archivo markdown](https://guides.github.com/features/mastering-markdown/)

## Clonando un repositorio

Al crear un repositorio en _Github_ se nos proporcionará una URL al mismo. Aquí se almacenarán todos los archivos y carpetas que vayamos añadiendo.

Creamos una carpeta en nuestro PC y, desde la consola, accedemos a esta carpeta y ejecutamos el siguiente comando:

`git clone url`

donde `url` es la URL a nuestro repositorio en _Github_.

Podremos clonar el repositorio sin encontrarnos dentro de la ruta donde queremos instalarlo añadiendo la ruta como parámetro:

`git clone url local_path`

## Etapas del control de código

### Staging

Cada modificación que se quiera "enviar" a Github debemos **hacer un _staging_**. En la consola, y desde dentro del directorio, se realiza con:

`git add README.md`

También se puede hacer desde el _source control_ (menú lateral izquierdo).

Con el comando `git status` podremos comprobar en qué estado se encuentran los archivos del directorio respecto al repositorio en Github. Si aparece en verde los archivos estarán en estado `staged`; si aparece en rojo se nos mostrará qué le sucede a cada archivo.

Al haber realizado el _staging_ del archivo, también nos aparecerá en el _source control_ de VSCode como _staged_ automáticamente.

Para hacer un _staging_ de todos los archivos pendientes, basta con ejecutar

`git add .`

### Commit

Pero estos cambios no son definitivos en el repositorio. Para ello hay que **hacer un _commit_**. Para ello escribiremos en la consola:

`git commit -m "mensaje o descripción"`

El parámetro (opcional) `-m` es una cadena de texto que deberá ir entre comillas e indicará una breve descripción para el `commit`.

En este punto habremos hecho nuestro primer `commit`.

Aparecerá un feedback con los archivos que han cambiado respecto a la versión que se encontraba en el repositorio y cuántas inserciones se han realizado en él.

Con `git status` podremos ver que ya no aparece ningún archivo (no queda ningún archivo `staged` pendiente de `commit`).

### Push

El último paso es enviar (`push`) el archivo a _Github_. Para ello usaremos el siguiente comando:

`git push origin master`

El `origin` es el _branch_ (que veremos más adelante) y el `master` es el _branch_ maestro, el que podemos ver en la raíz de nuestro repositorio.

Se nos pedirán las credenciales de _Github_ para poder hacer el `push` y, una vez proporcionadas, nuestro archivo habrá llegado a la plataforma. Existen [claves públicas SSH](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh) para instalar en el PC que evitan esta constante petición de credenciales.

Si visitamos el índice de nuestro repositorio en _Github_ veremos nuestro archivo .md en la raíz del mismo.

## Comandos importantes

### Diff

Con este comando podremos ver las diferencias entre la versión que tenemos en local y la que se encuentra en el repositorio.

`git diff <archivo>`

Las líneas discordantes se mostrarán con un `-` delante de ellas y un color determinado tal y como aparecen en el en el repositorio, y con un `+` y otro color tal y como aparecen en nuestro archivo local.

Por lo que estoy comprobando es más sencillo ver las diferencias entre archivos en VSCode.

### Log

Con este comando podemos ver los `commit` que hemos realizado sobre los arhivos.

`git log`

Aquí veremos información como las descripciones de los `commit` (que añadimos con el parámetro `-m` al realizarlos), los _branches_ donde se encuentran los archivos, etc.

Desde nuestro repositorio en _Github_ podremos ver todos los cambios que han sufrido nuestros archivos, así como el autor de los mismos y la fecha en la que se realizaron.

### Un log especial

Para que se muestren los resultado de un `log` de manera mucho más visual, bien ordenados y coloreados para identificar todos los datos bien, creamos un alias del siguiente comando en la consola

`git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"`

 y luego ejecutamos el alias

 `git lg`

## Recuperando archivos anteriores

Cuando hacemos un `git log` recuperamos todas las versiones de un archivo junto a un _hash_ que lo identifica.

Copiando parte de ese _hash_ (no es necesario todo) y ejecutando el comando 

`git checkout <hash>`

se recuperará en nuestro editor el archivo.

Podremos hacer cambio e incluso guardarlo abriendo un _branch_ nuevo para no sobreescribir archivos posteriores.

Si queremos volver a la última versión sobre la que se ha hecho `commit` podremos hacerlo con un 

`git checkout master`
