# Example repository
Este es el primer ejercicio del curso de Udemy _Git & Github Crash Course: Create a Repository From Scratch!_ del Kalob Taulien

.md -> markdown
[Markdowns](https://guides.github.com/features/mastering-markdown/)

Cada modificación que se quiera "enviar" a Github debemos **hacer un _staging_**. En la consola, y desde dentro del directorio, se realiza con:

`git add README.md`

También se puede hacer desde el _source control_ (menú lateral izquierdo).

Con el comando `git status` podremos comprobar en qué estado se encuentran los archivos del directorio respecto al repositorio en Github. Si aparece en verde los archivos estarán en estado `staged`; si aparece en rojo se nos mostrará qué le sucede a cada archivo.

Al haber realizado el _staging_ del archivo, también nos aparecerá en el _source control_ de VSCode como _staged_ automáticamente.

Pero estos cambios no son definitivos en el repositorio. Para ello hay que **hacer un _commit_**. Para ello escribiremos en la consola:

`git commit -m "mensaje o descripción"`

El parámetro (opcional) `-m` es una cadena de texto que deberá ir entre comillas e indicará una breve descripción para el `commit`.

En este punto habremos hecho nuestro primer `commit`.

Aparecerá un feedback con los archivos que han cambiado respecto a la versión que se encontraba en el repositorio y cuántas inserciones se han realizado en él.

Con `git status` podremos ver que ya no aparece ningún archivo (no queda ningún archivo `staged` pendiente de `commit`).