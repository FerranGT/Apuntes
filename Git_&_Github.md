#GIT

Entramos en la shell y comprobamos si esta instalado

`git version` nos dice la version o que no esta instalado, sino lo instalmos

#Configuracion inicial de GIT

`git config --global user.name "Mi nombre"`
`git config --global user.email "Mi email"`
`git config --global color.ui auto`

#Starting with an Unversioned Project

`cd path/to/project/folder` ruta donde va estar la carpeta con nuestro proyecto

`git init` se crea la carpeta oculta .git que esta vacia lo comprobamos con `ls-la`

`git status` nos permite ver todos los archivos que tenemos en el staging area para comitear -> pasarlos al repositorio local. Como aun no hemos añadido ningun archivo al staging area ni al repositorio los archivos que tengamos en esta carpeta nos saldran como **untracked**

`git add nombre del archivo` añadimos el archivo al staging area
`git add '*.txt'` añadimos todos los archivos .txt
`git add --all` añade todo los archivos

`git status` nos permite ver todos los archivos que tenemos en el staging area para comitear -> pasarlos al repositorio local

`git checkout + file name` chequear los cambios en archivo

`git reset + file name` remove from the staging area

`git rm + file name` elimina el archivo, luego hay que hacer un git commit para que desaparezca el archivo del repositotio y luego git push.. para eliminarlo del github, para eliminarlo del local rm + file name

`git commit -m "La descripcion que queramos"` pasamos todos los archivos de la staging area al repositorio local la carpeta .git

`git log` Nos permite ver el historial de archivos comiteados, cada commit tiene un Commit Hash, Author Name & Email, Date

`git branch + file name`
Creamos una copia del archivo haciendo una rama

`git merge + file name`
Nos permite unir los archivos que hicimos una rama

`git checkout master` 
get back to the “current” state (latest commit) of the project

Para crera una **CARPETA** nueva simplemente la creamos en el terminal o en el finder dentro de la carpeta que hicimos el git init, luego entramos en la nueva carpeta y añadimos y comiteamos los archivos que queramos al repositorio



#GIT Connecting a Remote Repository & GitHub

`git remote add <name> <url>` 
Para conectarnos a un repositorio remoto
<name> as a convenient shortcut for <url> in other Git commands
<url> ponemos la direccion del reposotirio remoto al que nos queremos conectar
ejemplo `git remote add origin https://github.com/FerranGT/demo-git`
        `git remote add origin https://github.com/FerranGT/demo-git-2` 
        `git remote add origin https://github.com/FerranGT/notes-bootcamp` 



`git remote rm <name>`
ejemplo `git remote remove origin` elimina el link que hay con el github
Remove the connection to the remote repository called <name>

`git remote rename <old-name> <new-name>`
Rename a remote connection from <old-name> to <new-name>.

`git remote`
List the remote connections you have to other repositories.

`git remote -v`

List the remote connections you have to other repositories, but include the URL of each connection.

`git push -u origin master`
Subimos los archivos de nuestro repositorio local al remoto
The name of our remote is origin and the default local branch name is master. The -u tells Git to remember the parameters, so that next time we can simply run git push and Git will know what to do.

`git pull origin master`
Bajamos los archivos del remoto al local

`git diff HEAD`
Nos permite comprobar si hay algun cambio en el repositorio que hemos bajado con el que teniamos en local

`git diff --staged`
Para ver los cambios en el staging area

`git clone + url`
Para clonar un repo del github

Si quiero tener permisos en repositorio del github que no es mio, en la web hay una opcion de fork y se copia en nuestro perfil


## Trabajando en equipo en GitHub

Antes de subir los cambios al Github con mis cambios, hacemos un git pull que sincroniza mis archivos con los que hay en el Github y hace un mix, entonces luego ya puedo hacer git push


git branch nos indica cuantas ramas tenemos abiertas

git branch + nombre de la rama a crear

git checkout + rama creada  me permite cambiar de rama

## Creando la rama gh-pages en el git hub que me sirve como servidor web

git branch gh-pages // me crea la rama en el repositorio local

git push origin gh-pages // me crea o actulaiza la rama en el github

La ruta de la web en el github es : https://ferrangt.github.io/"el nombre del repositorio"/

Todos los links a las librerias bootstrap angular etc, tienen que ser con https

p.ej: https://ferrangt.github.io/MotoLab/


##gh-pages

Publicar en git hub en la rama gh-pages

git checkout gh-pages // cambiamos a la rama gh-pages

git merge master // copiamos todo lo del master a la rama gh-pages

git push origin gh-pages



#Deleting a repository

Manually enter the URL for your repository's Settings page in your browser:

https://github.com/YOUR-USERNAME/YOUR-REPOSITORY/settings
Repository deletion buttonUnder Danger Zone, click Delete this repository.

Read the warnings.

Deletion labelingTo verify that you're deleting the correct repository, type the name of the repository you want to delete.

Click I understand the consequences, delete this repository.



#initiliaze a git repository

`git init`


#add this new file to the repo

`git add readme.md`


#commit the change

`git commit -m "readme.md added"` 


#add 2 more interesting ideas to the README.md

`modifico este archivo`


#add this new file to staging

`git status` veo el status del repositorio
`git add readme.md`


#commit this new change

`git commit -m "descripcion de todos los cambios que se van a comitera"` 


#check the log of commits

`git log`


#Create a remote repo on github called notes-bootcamp

#Add this remote repo (git remote add) to your local repo

`git remote -v` te dice donde esta el git remoto
 `git remote add origin https://github.com/FerranGT/notes-bootcamp.git`


#push your changes to the remote repo

`git push -u origin master`


check changes: `git log`

para añadir al staging arear `git add + file name` para quitar `git reset + file name`


`git checkout + file name` descarta los cambios y regresa a la ultima version commiteada


Para clonar un repo del github: `git clone + url`

Para abrir un archivo desde el terminal al sublime `subl .`  te abre la carpeta


Para salir del editor vi, esc :q!

Si quiero tener permisos en repositorio del github que no es mio, en la web hay una opcion de fork y se copia en nuestro perfil

`git remote remove origin` elimina el link que hay con el github tenemos que hacer otra vez `git remote add origin + el link al repositorio remoto`


#Volver a una versión anterior de Git perdiendo lo posterior a ese commit

# Vemos el log de los commit:
git log --pretty=oneline

# Se muestra algo como ésto
5542cd7844e3a035542cd7848c19482029963813 cambios 3
0bbfc3d4b41c8cb572ad780a346ddfbb0f5cfed5 2
f03af74db09f6f1802024af5c1371756b5b9a557 1
f64da54ea58649f863cbddfdeadf67dbd046d7d8 :boom::camel: Added .gitattributes & .gitignore files

# Si queremos volver a como estaba todo cuando hicimos el commit 1 (perdiendo lo posterior al commit 1)
git reset --hard f03af74db09f6f1802024af5c1371756b5b9a557 

# No hacer git push al directorio remoto por que perderemos todo lo que teníamos.

# Para volver al presente basta con hacer un git pull. De esta forma se sincronizará el local con el contenido del repositorio remoto













