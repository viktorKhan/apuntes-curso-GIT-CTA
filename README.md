﻿prueba
======

#Repositorio de prueba

##Comandos útiles

* git <command> -h, muestra las opciones del comando indicado
* git config --list (mostrar configuración global)
* git config propiedad "valor" (guarda en la propiedad en la configuración del proyecto)
* git config --global user.name "me"
* git config --global user.email "me@email.com"
* git init (creado proyecto "curso")
* git status
* git clone
* git log (histórico commits)
* git log --oneline (formato bonito)
* git show (mostrar info del commit)


* git rm --cached <file> para mover de la zona de staging/index cuando NO HAY COMMITs todavía
* git reset HEAD <file> para mover de la zona de staging/index cuando HAY COMMITS
* git rm <file> para añadir el fichero borrado a la zona de staging/index
* git add <file> para añadir ficheros añadidos o modificados a la zona de staging/index
* git checkout <revision|nombre de la rama> mueve el puntero a la revisión o rama indicada
* git stash, sólo funciona con ficheros que están en la zona de staging/index
* git stash list, para ver todos los commits que hay en la zona de stash
* git stash apply, recupera el último commit de la zona de stash
* git stash apply <identificador, stash@{n}>, recupera el commit indicado por el identificador
* git stash save "mensaje", guarda en la zona de stash con un mensaje personalizado
* git stash pop, recupera el commit y lo borra de la zona de stash
* git stash drop <id>, elimina el commit de la zona de stash indicado por el identificador
* git stash clear, borra toda la zona de stash
* git show <id_stash>, muestra la información básica sobre el commit realizado en la zona de stash
* git log --oneline -- <file>, busca todos los commits que contengan un fichero
* git checkout <revision> -- <file>, trae la versión del fichero correspondiente a la revisión.
* git commit -am "message", comitea los ficheros trakeados de una vez, suma de add + commit.
* git commit -m "message" <file>, solo hace commit del fichero indicado
* git commit --amend, los cambios se añaden al último commit
* git checkout master^, vuelve al commit anterior
* git checkout master^^, vuelve al penúltimo commit
* git checkout master~2, vuelve al penúltimo commit
* git checkout -- <file>, 
* git diff -w master origin -- <file>, compara un fichero entre dos ramas
* git log master~12..master~10, muestra los commits que van del doceavo al décimo
* git log --grep='reg-exp', obtiene los commits que coinciden con la expresión regular 'reg-exp'
* git log --no-merges, mustra todos los commits salvo los que son de mergeo
* git log [--since|--before|--after]={2014-04-18}, muestra los commits desde, anteriores o posteriores a la fecha indicada
* git log --abbrev-commit, muestra el ID de commit abreviados
* git log --stat, muestra los ficheros cambiados en cada commit
* git --decorate --graph --oneline --all, el --all incluye las ramas en el gráfico

##Deshacer cambios
* git checkout -- <file>, descarta los cambios realizados en la zona de trabajo y recupera los del último commit

##Deshacer commits
* git reset --hard <commit-id>, <b>elimina los cambios</b> posteriores al commit indicado
* git reset --soft <commit-id>, descarta los commits posteriores al commit indicado pero <b>mueve los cambios a la zona de stagging/index</b>
* git reset --mixed <commit-id>, descarta los commits posteriores al commit indicado pero <b>mueve los cambios a la zona de working</b>
* git gc --force, purga los commits eliminados
* git revert <commit-id>, <b>crea un nuevo commit</b> con lo contrario del commit especificado
* git branch -a, mustra todas las ramas, incluso las remotas
* git branch -d <branch>, borra ramas que ya han sido mergeadas
* git branch -D <branch>, borra ramas aunque no hayan sido mergeadas
* git push <remote> :<branch>, borrar una rama remota
* git branch <local-branch> <repo>/<remote-branch>, me crea una rama trayéndome lo que hay en la rama remota
* git checkout -b <local-branch> <repo>/<remote-branch>, me crea una rama trayéndome lo que hay en la rama remota y me posiciona
* git reset --hard orig_head, hace el reset y vuelve al commit donde anteriormente estaba HEAD, sea en la rama que sea.

##Ramas
git rebase master, añade los commits de master a mi rama
git rebase -continue, continua con el rebase si ha dado conflictos

##Mergeos
* git merge rama1 --no-ff, si hay posibilidad de hacer Fast Forward, no lo hace y crea un commit de mergeo
* git config branch.mergeoptions "--no-ff", configuramos a nivel de proyecto que al mergear cualquier rama no se haga un Fast Forward.


##Remotos
* git remote add <upstream> <url_repo>, enlazamos con un repo remoto distinto a origin (se suele llamar upstream)
* git pull upstream master, nos traemos el código del repo remoto al que hemos enlazado
* git fetch origin master, te trae los cambios de la rama master de remoto y los guarda en origin/master, pero NO los mergea
* git push -f <repo> <branch>, machacas lo que hay en el remoto con mi local


#Tips:

* Para salir de git log, pulsar "q"
* Crear siempre un primero commit tonto, por ejemplo con un fichero readme.txt
* Para obtener el caracter ~, pulsar AltGr-4-espacio
* User DiffMerge como utilidad para comparar merges en GIT
* Hacer "squashing", aplanar commits, juntar varios commits en uno
* Hacer "spliting", dividir un commit en n commits
* ¿Hacer rebase o mergeos?
* Merge de tipo "Fast Forward", avanzar n commits
* Al crear una rama llamada "gh-pages", todo lo que suba a esa rama lo publicará en una URL (nombreUsuario.github.io.nombreProyecto). Motor de plantillas de Jekyll para darle estilos a la página (http://jekyllthemes.org/).


#Revisar:

* Rebase interactive
* Continuous delivery - Martin Fowler (feature branch / feature toogle)
* Entender el flujo de GitHub para poder contribuir en un proyecto, https://guides.github.com/introduction/flow/index.html
* Git Flow, http://nvie.com/posts/a-successful-git-branching-model/



#Ejercicios:

1. En un repo nuevo o existente, crear un fichero "nombre.txt", borrar fichero y hagamos un commit. Recuperar el fichero. 

* touch prueba.txt
* git add prueba.txt
* git commit -m "Añadimos el fichero prueba.txt"
* rm prueba.txt
* git add prueba.txt
* git commit -m "Eliminamos el fichero prueba.txt"
* git reset master^

2. Borrar dos ficheros y hacmos commit con los dos y recuperar sólo uno de ellos.

* touch prueba.txt
* touch hola.txt
* git add .
* git commit -m "Añadimos los ficheros prueba.txt y hola.txt"
* rm prueba.txt
* rm hola.txt
* git commit -am "Borramos los ficheros prueba.txt y hola.txt"
* git reset master^
* git add prueba.txt
* git commit -m "Añadimos el fichero prueba.txt"


3. Avanzar master dos commits, crear una rama con esos dos commits y dejar master sin esos dos commits
* git branch rama1
* git reset master~2 --hard
