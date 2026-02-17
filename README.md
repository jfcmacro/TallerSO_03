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
find . -name .keep -exec git add {} \;
find . -name makefile -exec git add {} \;
```

Acometa (*commit*) el proyecto.

```
git commit -m "Iniciando el Taller 03"
git push
```

## Interpretador de comandos

### Comandos vistos en anteriormente

* `echo`: Imprime un mensaje en la salida estándar.
* `ls`: lista los nombres de los ficheros.
* `cat`: Muestra el contenido de un fichero.
* `wc`: Cuenta el número de palabras, caráteres y líneas.

### Sistema de ayuda interactiva

* `man`
* `apropos`: 
* `info`:
* La opción `--help` ó `-h`
* El comando `help` de `bash`
* [Man online](https://man7.org/linux/man-pages/)
* `zeal`
* [DevDocs](https://devdocs.io/)
* Obteniendo ayuda
* [Learn Microsoft](https://learn.microsoft.com/)

### Directorio de trabajo

Abra una ***nueva*** terminal. 

Ejecute el siguiente comando en la nueva terminal:

```bash
pwd
```

Este comando muestra el directorio de trabajo actual.

Muestre el contenido del directorio

```bash
ls -la
```

Debe haber varios directorios especiales, en particular dos:  `.` directorio de actual, `..` padre

Cambie al directorio padre

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

Hay varias formas de volver al directorio del usuario: `cd $HOME` ó `cd ~` ó `cd`. 

Ejecute los siguientes comandos,  todos ellos te volverán a traer al directorio `$HOME`. 

 ```bash
 cd /
 cd $HOME
 pwd
 cd /
 cd ~ 
 pwd
 cd /
 cd
 pwd
 cd /
 cd $OLDPWD
 pwd
 ```

Una mención especial con el comando `cd $OLDPWD`, este volverá al directorio anterior, si esta ubicado en un directorio distinto y se mueve a otro directorio, volverá al directorio original del anterior `cd`.

```bash
cd /
pwd
cd /tmp
pwd
cd $OLDPWD
pwd
```

### Manipulando ficheros

* `cp`: Copia un fichero a otro
* `mkdir`: Crea un directorio
* `mv`: Renombrar o mover un fichero
* `ln`: Enlazar un fichero
* `rmdir`: Borrar un directorio
* `rm`: Borrar un fichero

**[Ejercicio 1]**

1. Abrir una terminal. Ir a la carpeta (directorio) que contiene el taller actual, y buscar el directorio nombrado `bash_01`.

2. Crear un directorio en esta carpeta llamado `datos_01`.
3. Copiar del directorio base del taller actual el fichero `<taller_actual>/data/datafile`, dentro de la carpeta `datos_01`.

4. Renombrar el fichero `datafile` con el nombre fichero: `fichero_datos.txt`
5. Crear dos carpetas (directorio) dentro la carperta `bash_01` llamadas `datos_02`, `datos_03`. 
6. Crear un enlace duro entre la carpeta `datos_01/fichero_datos.txt`  al fichero  `datos_02/fichero_datos.bak`
7. Crear un enlace duro entre la carpeta `datos_01/fichero_datos.txt` al fichero `datos_03/fichero_datos.bak`
8. Crear un enlace símbolico entre la carpeta `datos_01/fichero_datos.txt` al fichero `datos_02/fichero_datos.sim`
9. Borrar la carpeta `datos_03`. 

### Comandos básicos

* `head`
* `tail`
* `cut`
* `grep`
* `sort`
* `uniq`

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

Con los comandos aprendidos hacer los siguiente ejercicios. El separado por omisión es el carácter `|`

**[Ejercicio 2]**. (Carpeta: `bash_02`  Nombre: `ordenar.sh` )

* Formato: `ordenar.sh <nombre_fichero> <columna>`
* Descripción: dado un `<nombre_fichero>` y una `<columna>` obtener los valores de esa `<columna>` ordenados descendentemente. Puede haber valores repetidos. Ni líneas en blanco.

**[Ejercicio 3]**. (Carpeta: `bash_02` Nombre: `unico.sh`)

* Formato: `unico.sh <nombre_fichero> <columna>`
* Descripción: dado un `<nombre_fichero>` y una `<columna>`obtener los valores de esa `<columna>` unicos. No puede haber valores repetidos. Ni líneas en blanco.

**[Ejercicio 4]**. (Carpeta: `bash_02` Nombre: `eliminar_punto_keep.sh`

Mire lo que hace la instrucción `find` al principio del documento y entienda que hace.

* Formato: `eliminar_punto_keep.sh <directorio_trabajo>`
* Descripción:  dado un `<directorio_trabajo>` eliminar todos los ficheros `.keep`  recuerde que estos fichero pueden estar bajo el control de versiones (`git`), utilizar para ello `git-rm`.

### Información del estado del sistema

* `who`: muestra quien esta conectado en el sistema
* `ps`: reporta una imagen actual de los procesos
* `top`: muestra los procesos actuales

Para los siguiente ejercicios `bash` tiene una variable llamada `$USERNAME`, esta contiene el nombre usuario actual.

**[Ejercicio 5]**. (Carpeta `bash_02` Nombre: `mis_procesos.sh`)

* Formato: `mis_procesos.sh` 
* Descripción. Debe mostrar los procesos actuales del usuario.

**[Ejercicio 6]**. (Carpeta `bash_02` Nombre: `mi_top.sh`)

* Formato: `mi_top.sh`
* Descripción. Debe mostrar en top solamente los procesos del usuario actual.
