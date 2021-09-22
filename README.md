# Instalación de Git en Linux

En el siguiente informe se va a detallar las distintas formas de instalar Git en Linux y realizar su correspondiente configuración para su correcto funcionamiento.

# Requerimientos
Será necesario Debian 11 o cualquier otra distro Linux, acceso a internet y permisos de administrador para el usuario.

# Instalación de Git con los repositorios del sistema

Antes de comenzar confirmar si Git está instalado en nuestro sistema, ya que hay distribuciones que integran dicha herramienta:

```
git --version
```

Si lanza el resultado siguiente es que no está instalado:

```
bash: git: orden no encontrada
```

Por el contrario, si lanza una sentencia similar a la siguiente, significa que si está instalado:

```
git version 2.27.1
```

En el caso de que ya esté instalado puede continuar con la siguiente guía para actualizar a la versión más estable de sus repositorios o continuar con la [Instalación de Git desde la fuente]() para buscar la versión más reciente de la herramienta.

Continuar actualizando los repositorios del sistema con la herramienta de administración de paquetes ***apt***

```
sudo apt update
```
Completada la actualización puede instalar Git:

```
sudo apt install git
```
Confirmar que se ha instalado correctamente con el siguiente comando:

```
git --version
```

**Output**
```
git version 2.30
```
Tras haber instalado Git correctamente puede pasar a la sección [Configuración de Git]() de esta guía.

# Instalación de Git desde la fuente
Antes de comenzar, se debe instalar el software necesario para Git:
```
sudo apt install libz-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext cmake gcc
```
Crear un directorio donde almacenar el fichero comprimido de la herramienta y realizar la instalación. Acceder a la misma para descargar el fichero.

```
mkdir tmp
cd /tmp
```
Las versiones de Git se pueden encontrar en [página oficial](https://mirrors.edge.kernel.org/pub/software/scm/git/) de la herramienta.

Para descargar cualquier versión utilizaremos la herramienta de la línea de comandos ***curl*** de la siguiente forma:

```
curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.30.0.tar.gz
```
desde la última / adelante sería modificable según versión.

Descomprimir el fichero descargado:

```
tar -zxf git.tar.gz
```

Acceder al directorio creado tras descomprimir

```
cd git-*
```

Ahora, se podrá crear el paquete e instalarlo escribiendo estos dos comandos:

```
make prefix=/usr/local all
sudo make prefix=/usr/local install
```

Sustituir el proceso de shell para que se utilice la versión de Git que acabamos de instalar:

```
exec bash
```

Confirmar que la instalación se realizó correctamente comprobando la versión.

```
git --versión
```
**Output**  git version 2.30.0 

La versión debería ser la correspondiente a la descargada.

# Configuración de Git

Para realizar la configuración debemos proporcionar nuestro nombre de usuario y dirección de correo de ***Github*** de la siguiente forma:

```
git config --global user.name "Your UserName"
git config --global user.email "youremail@domain.com"
```
Podemos ver la configuración introducida escribiendo lo siguiente:

```
git config --list 
```

La información que ingresa se almacena en el archivo de configuración de Git. Podrá ser editado de la siguiente forma:

```
vim ~/.gitconfig
```
Pulsar Esc y escribir :wq para salir del editor.

Existen otras formas como clonar el repositorio oficial de Github de esta herramienta, pero las dos descritas anteriormente son las más comunes.





