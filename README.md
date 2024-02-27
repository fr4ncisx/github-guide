# GitHub Guide:

#### [GIT CONFIG](#git-config)
- Configurar tu cuenta de github
#### [GIT INIT](#git-init)
- [Guia: Inicialización de repositorio](https://www.aluracursos.com/blog/iniciando-repositorio-con-git)
#### [GIT LOG](#git-log)
- Ver movimientos en tu repositorio
#### [GIT ADD](#git-add)
- Subir archivos a tu repositorio
#### [GIT BRANCH](#git-branch)
- Crear, modificar, eliminar branches
#### [GIT MERGE](#git-merge)
- Fusionar branches


## <span style="color:yellow"> GIT CONFIG </span>
##### Ver configuración global
``git config --global -e ``
##### Designar tu usuario de github
``git config --global user.name "tu-nombre-de-usuario"``
##### Designar tu correo de github
``git config --global user.email "tu-correo@mi-correo.com"``

## <span style="color:yellow">GIT INIT
##### Inicializar nuestro repositorio
``git init``

##### Agregar archivos a un repositorio vacío
1. ``git remote add origin <repo-url>``
2. ``git push -u origin <nombre-de-tu-rama>``
##### El -u establece la rama remota como la rama de seguimiento (tracking branch), lo que simplifica los futuros comandos git push.


## <span style="color:yellow">GIT CLONE
##### El más básico del git clone, para clonar un repositorio.
``
git clone <repo-url>
``

##### Clona el repositorio ubicado en ＜repo-url＞ en la carpeta llamada ~＜directory＞! en la máquina local.
``
git clone <repo-url> <directory>
``

##### También puedes configurar el git clone y clonar el repositorio desde una branch específica, diferente a la original, de esta manera:
``
git clone -b <branchname> <remote-repo-url>
``
##### En el ejemplo anterior se clonaria solamente la branch <branchname> de repositorio. 



## <span style="color:yellow">GIT LOG

##### Podemos visualizar todos los commits, uno en cada línea con el comando:
``git log –oneline``

##### Si, en lugar de menos informaciones, queremos ver más, como las alteraciones del commit, podemos usar:
``git log -p``

##### También podemos buscar las informaciones de la persona autora del commit con el comando:
``git log --author="user_name"``

##### Y buscar informaciones por fecha:
``git log --since=1.month.ago --until=1.day.ago``
##### En el comando anterior, estamos buscando las informaciones del commit desde hace un mes hasta hace un día.

##### Tu también puedes formatear la visualización de las informaciones del commit con el comando:
``git log --pretty="format:%h %s"``
 

## <span style="color:yellow">GIT ADD
### Orden para subir un archivo en GitHub:

##### Subir solo un archivo en éste caso 'index.html'.
``git add index.html`` 


##### Subimos todos los archivos.
``git add .``

``git commit -m "Mensaje commit de los archivos subidos"``
 
##### Finalmente 
``git push ``

##### Podemos también hacer un PUSH a otra BRANCH
``git push origin <new-branch>``

<span style="color:red; font-size: 15px; font-weight: bold;">  TIP: Puede existir o no la new-branch. Ya que la creara.
 
##### PODEMOS USAR 
##### Para ver si los archivos se subieron (color verde)
`` git status ``

##### Te muestra en la consola que se modifico en el archivo 'index.html'
``git diff index.html``

##### Devolver el index.html al commit anterior
``git restore index.html``

##### Podemos usar también para devolver todos los archivos del último commit.
``git restore . ``
 

## <span style="color:yellow">GIT BRANCH
##### Vemos las ramas existentes
``git branch``


##### Creamos la branch rama_desarollo
``git branch rama-desarrollo``


##### Cambiamos a rama_desarrollo
``git checkout rama-desarrollo``


#### Tenemos también otra forma más simplificada

##### Creamos la nueva branch y cambiamos a esa rama
``git checkout -b rama-desarrollo``


##### También podemos modificarla
##### Le cambiamos el nombre de 'rama-desarrollo' a 'dev-branch'
``git branch -m rama-desarrollo dev-branch``


##### Eliminar la branch
``git branch -d dev-branch``
##### También podemos ver las ramas existentes usando 
``git branch``
##### Y después usamos para cambiar a la siguiente rama de la lista 
``git switch <nombre-de-la-rama>``

## <span style="color:yellow">GIT MERGE

##### Tenemos dos branch (main y dev-branch)
1. Como primer instancia switcheamos a la branch main
``git switch main``
2. Luego hacemos el merge de la rama dev-branch
``git merge dev-branch``
3. Verificamos con git log
``git log --oneline``
4. Hacemos el push a la rama main
``git push origin main``

##### Lo que hicimos acá es dejar todo exactamente como estaba en dev-branch
##### Pero lo aplicamos en la branch main