# Taller 3

## Agenda

1. Preliminares
2. Interpretador de comandos

## Preliminares

Abra una terminal. Abra el directorio de repositorio y de los talleres

```
cd <repositorio-enlace>
cd talleres
```

Descargue el taller en formato zip, descomprimalo.

```
wget https://github.com/jfcmacro/TallerSO_03/archive/refs/heads/master.zip
unzip master.zip
rm master.zip
```

Mire la estructura actual

```
tree .
```

Entre al directorio del taller

```
cd TallerSO_03-master
```

Adicione los ficheros

```bash
git add README.md .gitignore
```

Adicione los ficheros del proyecto, esto adiciona todos ficheros del taller.

```bash
find . -name *.c -exec git add {} \;
find . -name makefile -exec git add {} \;
```

Acometa (*commit*) el proyecto.

```
git commit -m "Iniciando el Taller 03"
git push
```

## Interpretador de comandos

### Comandos vistos en anteriormente

* `echo`
* `ls`
* `cat`
* `wc`

### Sistema de ayuda interactiva

* `man`
* [Man online](https://man7.org/linux/man-pages/)
* `zeal`
* [DevDocs](https://devdocs.io/)

### Directorio de trabajo

Abra una terminal. 

Ejecute el siguiente comando

```bash
pwd
```

Este comando muestra el directorio de trabajo actual.

Muestre el contenido del directorio

```bash
ls -la
```

Debe haber varios directorios especiales, en particular dos:  `.` directorio de actual, `..` padre

Cambie directorio al directorio padre.

```bash
cd ..
```

Mire la estructura de directorios.

```
tree .
```

Revise el manual `man tree` y pruebe varias opciones.

Mire el contenido del directorio con el comando `ls`. Revise el manual `man ls` y pruebe varias opciones.

Muévase al directorio de raíz:

```bash
cd /
```

Mire la estructura de directorios con `tree` y pruebe varias opciones.

Hay varias formas de volver al directorio del usuario: `cd $HOME`, `cd ~`, `cd`. 

### Manipulando ficheros

* `cp`: Copia un fichero a otro
* `mkdir`: Crea un directorio
* `mv`: Renombrar o mover un fichero
* `ln`: Enlazar un fichero
* `rmdir`: Borrar un directorio
* `rm`: Borrar un fichero

### Comandos básicos

* `head`
* `cut`
* `grep`
* `sort`
* `uniq`
* 

### Ejecución de programa

* Estructura de la línea de comandos:
  * Comandos
  * Opciones
  * Argumentos
* Comandos
  * Programas. Todo ejecutable, con la ruta de camino o que se encuentre en la variable `$PATH` y que se tenga permisos, puede ser ejecutada
  * Ordenes internas
* Opciones
* Argumentos
  * Variables
  * Salida de otros programas como argumentos

### Información del estado del sistema

* `who`: 
* `ps`
* `top`

### Lenguaje de programación

