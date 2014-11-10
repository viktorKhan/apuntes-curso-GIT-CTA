prueba
======

Repositorio de prueba

-- Comandos �tiles

git config --list (mostrar configuraci�n global)
git config propiedad "valor" (guarda en la propiedad en la configuraci�n del proyecto)
git config --global user.name "me"
git config --global user.email "me@email.com"
git init (creado proyecto "curso")
git status
git clone
git log (hist�rico commits)
git log --oneline (formato bonito)
--> En Windows, para salir del git log, presionar "q"
git show (mostrar info del commit)


git rm --cached <file> para mover de la zona de staging/index cuando NO HAY COMMITs todav�a
git reset HEAD <file> para mover de la zona de staging/index cuando HAY COMMITS
git rm <file> para a�adir el fichero borrado a la zona de staging/index
git add <file> para a�adir ficheros a�adidos o modificados a la zona de staging/index
git checkout <revision|nombre de la rama> mueve el puntero a la revisi�n o rama indicada
git stash, s�lo funciona con ficheros que est�n en la zona de staging/index
git stash list, para ver todos los commits que hay en la zona de stash
git stash apply, recupera el �ltimo commit de la zona de stash
git stash apply <identificador, stash@{n}>, recupera el commit indicado por el identificador
git stash save "mensaje", guarda en la zona de stash con un mensaje personalizado
git stash pop, recupera el commit y lo borra de la zona de stash
git stash drop <id>, elimina el commit de la zona de stash indicado por el identificador
git stash clear, borra toda la zona de stash
git show <id_stash>, muestra la informaci�n b�sica sobre el commit realizado en la zona de stash
git log --oneline -- <file>, busca todos los commits que contengan un fichero
git checkout <revision> -- <file>, trae la versi�n del fichero correspondiente a la revisi�n.
git commit -am "message", comitea los ficheros trakeados de una vez, suma de add + commit.
git commit -m "message" <file>, solo hace commit del fichero indicado
git commit --amend, los cambios se a�aden al �ltimo commit



Tips:

- Crear siempre un primero commit tonto, por ejemplo con un fichero readme.txt


Revisar:

-- Rebase interactive