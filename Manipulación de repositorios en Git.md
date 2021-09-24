En el siguiente repositorio se llevará a cabo una serie de procesos para habituarnos con la creación y manipulación de repositiorios en ***Git***.

# Requisitios previos
Disponer de una distribución Linux con los pasos realizados en el [anterior repositorio](https://github.com/gdborja/git/blob/main/Instalacion%20de%20Git%20en%20Linux.md).

# Configuración

Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida.

```
  git config --global user.name "Your-Full-Name"
  git config --global user.email "your-email-address"
  git config --global color.ui auto
  
```

Mostar la configuración final.
```
git config --list
```

# Creación de un repositorio

Crear un repositiorio nuevo y mostrar su contenido.

```
mkdir dpl
 cd dpl
 git init
 ls -la
```

# Realización de tareas en el repositorio

Comprobar el estado del repositorio.

```
git status
```

Crear un fichero indice.txt con el siguiente contenido:
<ul>
<li>Capítulo 1: Instalación de Git </li>
<li>Capítulo 2: Flujo de trabajo básico</li>
</ul>

```
cat > indice.txt
 Capítulo 1: Instalación de Git 
 Capítulo 2: Flujo de trabajo básico
 Ctrl+D
```

Comprobar de nuevo el estado del repositorio.

```
git status
```

Añadir el fichero a la zona de intercambio temporal.

```
git add indice.txt
```
Volver a comprobar una vez más el estado del repositorio.

```
git status
```

# Realizando Commit's

 Realizar un commit de los últimos cambios con el mensaje ***Añadido índice de la asignatura DPL.*** y ver el estado del repositorio.

```
git commit -m "Añadido índice de la asignatura DPL."
git status
``` 

# Modificación de ficheros

Añadir al fichero indice.txt los siguiente:

<ul>
<li>Capítulo 3: Gestión de ramas</li>
<li>Capítulo 4: Repositorios remotos</li>
</ul>

```
cat > indice.txt
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos
Ctrl+D
``` 

Mostrar los cambios respecto a la  última versión guardada en el repositorio.

```
git diff
```

Hacer un commit de los cambios con el mensaje ***Añadido los capitulos 3 y 4**.

```
git commit -m "Añadido los capitulos 3 y 4"
```

# Historial

Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

```
git show
```

Cambiar el mensaje del último commit por ***Añadido el capitulo sobre gestión de ramas al índice.***

```
git commit --amend -m "Añadido el capitulo sobre gestión de ramas al índice."
```

Volver a mostrar los últimos cambios del repositorio.

```
git show
```










