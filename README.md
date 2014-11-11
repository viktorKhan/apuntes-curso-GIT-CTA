prueba
======

#Repositorio de prueba

-- Comandos útiles

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
--> En Windows, para salir del git log, presionar "q"
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
<<<<<<< HEAD
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
* git checkout -- <file>, descarta los cambios realizados en la zona de trabajo y recupera los del último commit
* git reset --hard <commit-id>, *elimina los cambios* posteriores al commit indicado
* git reset --soft <commit-id>, descarta los commits posteriores al commit indicado pero *mueve los cambios a la zona de stagging/index*
* git reset --mixed <commit-id>, descarta los commits posteriores al commit indicado pero *mueve los cambios a la zona de working*
* git gc --force, purga los commits eliminados
* git revert <commit-id>, *crea un nuevo commit* con lo contrario del commit especificado
* git branch -a, mustra todas las ramas, incluso las remotas
* git branch -d <branch>, borra ramas que ya han sido mergeadas
* git branch -D <branch>, borra ramas aunque no hayan sido mergeadas
* git push <remote> :<branch>, borrar una rama remota
* git branch <local-branch> <repo>/<remote-branch>, me crea una rama trayéndome lo que hay en la rama remota
* git checkout -b <local-branch> <repo>/<remote-branch>, me crea una rama trayéndome lo que hay en la rama remota y me posiciona




#Tips:

* Crear siempre un primero commit tonto, por ejemplo con un fichero readme.txt
* Para obtener el caracter ~, pulsar AltGr-4-espacio
* User DiffMerge como utilidad para comparar merges en GIT
* Hacer "squashing", aplanar commits, juntar varios commits en uno
* Hacer "spliting", dividir un commit en n commits


#Revisar:

* Rebase interactive
* Continuous delivery - Martin Fowler (feature branch / feature toogle)

#Ejercicios:

1. En un repo nuevo o existente, crear un fichero "nombre.txt", borrar fichero y hagamos un commit. Recuperar el fichero. 

* touch prueba.txt
* git add prueba.txt
* git commit -m "Añadimos el fichero prueba.txt"
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
