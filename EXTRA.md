# Vídeos con información extra

Vídeos de [Git for Everybody](https://gitforeverybody.com/free-git-tutorials/)

## Deshaciendo un staging (unstaging)

Si, por error, hemos realizado un _staging_ de un archivo y, por ejemplo, lo hemos borrado de nuestro repositorio, es muy sencillo recuperarlo de nuevo.

`git reset HEAD <nombre_de_archivo>`

Importante `HEAD` en mayúsculas.

## Deshaciendo un borrado (undeleting)

Si hemos borrado totalmente el archivo de nuestro PC podemos recuperarlo con el siguiente comando:

`git checkout -- <nombre_del_archivo>`