# week1-course2-git-github

#Instalar git en linux
##Antes de instalar actualizar el sistema
sudo apt-get update
sudo apt-get upgrade

##Instalar git
sudo apt get install

#Comenzar en una carpeta un repositorio
git init

#Añadir archivo al repositorio
git add FileName.txt

# Enviar los ultimos cambios del archivo a la base de datos
git commit -m "Mensaje del commit"

Para guardar los cambios hechos a un archivo del repositorio
git add .
git commit -m "Mensaje referente a los cambios realizados"
git status
git show
git log FileName.txt
git push

Comandos git
git init -> Comienza un repositorio
git status -> Estatus del repositorio
git add FileName.txt -> agregar un archivo al repositorio

CONFIGURAR GIT
git config -> Muestra todo

git config --list -> Configuración por defecto y las que faltan
git config --list --show-origin -> donde están las configuraciones guardadas

Agregar en las configuraciones el nombre del usuario y el email:
git config --global user.name "Brenda M"
git config --global user.email "email@email.com"

agregar todos los archivos a la vez en un repositorio git add.

mostrar los commits hechos
git log FileName.txt

mostrar historia de un archivo (commits hechos)
git show historia.txt

git diff -> cambios en un archivo
git diff 8934... 3289...
se compara el codigo del commit de la versión vieja y el de la version nueva

<imagenes>
  git reset -> Borra todo lo que se ha hecho antes, volver a una version anterior
  git reset 897889... hard
  
  git log  --stat -> cambios especificos de los archivos en el commit
  git checkout -> cambiar de rama
  
  Git reset vs git remove
  git rm: Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones.
  Esto quiere decir que si necesitamos recuperar el archivo solo debemos "viajar en el tiempo" y recuperar el ultimo commit antes de borrar el archivo en cuestion
  Flags
  git rm --cached: Elimina los archivos del area de staging y del proximo commit pero los mantiene en nuestro disco duro.
  
  git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guardara todo, por lo que podemos acceder al registro de la existencia de los archivos (debemos usar comandos avanzados)
  Git reset
  Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. con git reset volvemos al pasado sin la posibilidad de volver al futuro.
  git reset --soft: Borramos todo el historial y los registros de Git pero  guardamos los cambios que tengamos en staging, asi podemos aplicar las ultimas actualizaciones a un nuevo commit
  
  
  git reset --hard Borra todo, abosultamente todo.
  
  IMPORTANTE
  git reset head: Este es el comando para sacar archivos del area de staging. No para borrarlos ni nada de eso, solo para que los ultimos cambios de estos archivos no se envien al ultimo commit a menos que cambiemos de opinion
  
