# ¿Qué es Git?

<br>
<br>

![img](../assets/ejercicio/git-logo.png)

<br>

>“Git es un **software de control de versiones** que permite llevar el registro de los cambios en los archivos de tu ordenador y coordinar el trabajo que varias personas realizan sobre archivos compartidos."<div style="text-align: right"> Wikipedia </div>

<br>
<br>

Nos permite trabajar en equipo de una manera mucho más simple y optima cuando estamos desarrollando software. En la actualidad es una herramienta imprescindible para cualquier desarrollador o equipo de desarrolladores.

Con **Git** podemos controlar todos los cambios que se hacen en nuestro código y tenemos control absoluto de todo lo que pasa con él, pudiendo **volver atrás en el tiempo**, **abrir diferentes ramas de desarrollo**, etc.

Cuando haces modificaciones en un fichero de código y haces un **commit**, Git almacena solo las líneas que has modificado desde tu útlimo **commit**.

<br>
<br>


# ¿Qué es GitHub?

<br>

![img](../assets/ejercicio/github-octocat.png)

<br>

Es un servicio basado en **Git** que nos provee la posibilidad de **alojar repositorios en la nube**. 

Un **repositorio** es una **carpeta controlada por Git**

Con GitHub podemos acceder de manera remota a nuestros repositorios, clonarlos, compartirlos con otros desarrolladores, etc. 

<br>
<br>


# Primeros pasos

<br>

1. Creamos una cuenta en [GitHub](https://github.com/).
2. [Instalamos](https://git-scm.com/downloads) y configuramos `Git` en nuestro ordenador.
3. Ingresamos a nuestra cuenta en `GitHub` y hacemos click en el botón para crear un `repositorio nuevo`.
4. Ingresamos el `nombre` de nuestro repositorio nuevo.
5. Elegimos si queremos que sea `público o privado`.
6. Elegimos si queremos inicializar nuestro repositorio con un fichero `README file`, un fichero `.gitignore `y/o` una licencia` (por el momento solo seleccionaremos la opción de añadir un fichero `README file`).
7. Hacemos click en `crear repositorio`.
8. Una vez dentro de tu repositorio de GitHub, clickeamos en `code` para copiar la url.
9. En la terminal abrimos la carpeta donde queremos hacer la copia de nuestro repositorio y lo clonamos con el comando `git clone <url>`
10. Con el comando `cd <nombre-del-repositorio>` ingresamos a la carpeta.
11. Abrimos nuestro repositorio en Visual Studio Code y hacemos las modificaciones que deseamos. Una vez terminado guardamos todo. 
12. Desde la terminal ejecutamos `git status` para visualizar qué ficheros han sufrido cambios y aún no están `commiteados`.
13. Ejecutamos `git add <nombre-de-los-ficheros-modificados>` o `git add -A` para agregar todos los ficheros al staging area.
14. Ejecutamos `git commit -m "<tu mensaje>"` para agregar un mensaje al commit que nos permita identificar los cambios realizados en esta versión del fichero.
15. Ejecutamos `git push` para subir todos los cambios que tenemos en local a nuestro repositorio remoto.

<br>
<br>

# Git environments: local vs remote
![img](../assets/git/git_environments.png)

# Git branches - Workflow para trabajar con ramas
![img](../assets/git/workflow_git.png)
![img](../assets/git/branches.png)
![img](../assets/git/branches.webp)
![img](../assets/git/branches_commands.png)


**GIT Working flow (local) - Ramas (Branches)**

Ramas (Universos Paralelos)
*Línea master -> linea estable o principal.*
*Lineas secundarias -> lineas de desarrollo, bugs, experimentos, etc...*

- branch

    - Crear una rama
    ```
    git branch NOMBRERAMA
    ```

    - Ver ramas
    ```
    git branch
    ```    

    - Cambiar de rama
    ```
    git checkout NOMBRERAMA
    ```  

    - Ver cambios en formato ramas
    ```
    git log --oneline --graph --all
    ```  

    - Borrar una rama
    ```
    git branch -d NOMBRERAMA
    ```


**GIT Working flow (local) - Fusiones (básico)**

- Nos situamos en la rama que absorberá (principal)
    ```
    git checkout RAMAPRINCIAL
    ```

- Hacemos el *merge*
    ```
    git merge RAMASECUNDARIA
    ```

- Añadir comentario (o)

- Guardar y salir (:x)

- Ramas fusionadas
    ```
    git branch
    ```

- Borramos rama
    ```
    git branch -d NOMBRERAMA
    ```


**GIT Working flow (local) - Fusiones (gestión conflictos)**

  - Fast-forward (automatizado). No hay conflicto alguno.

    - Nos situamos en la rama que absorberá (principal)
    ```
    git checkout RAMAPRINCIAL
    ```

    - Hacemos el MERGE
    ```
    git merge RAMASECUNDARIA
    ```

    - Añadir comentario (o)

    - Guardar y salir (:x)


  - Manual Merge (Conflicto, dos personas tocaron los mismos archivos)

    - Nos situamos en la rama que absorberá (principal)
    ```
    git checkout RAMAPRINCIAL
    ```

    - Hacemos el MERGE
    ```
    git merge RAMASECUNDARIA
    ```

    - En consola
    ```
    Auto-merging CARPETA/ARCHIVO
    CONFLICT (content): Merge conflict in CARPETA/ARCHIVO
    Automatic merge failed; fix conflicts and then commit the result.
    ```

    - En el editor
    ```
    <<<<<<< HEAD
    hello world....!!!!!!!
    =======
    hello world 2 ..!!!
    >>>>>>> conflictiva
    ```

    - Resuelver y guardar
    ```
    hello world 2 ..!!!
    ```

    - Comprobamos el estado
    ```
    git status
    ```

    - commit para la resolución conflicto
    ```
    git commit -am "con este commit se arregla el conflicto"
    ```

    - Resultado
    ```
    *   81a6c1d con este commit se arregla el conflicto
    |\  
    | * 64b5518 que pasa
    * | 29a6348 ahora conflcito..no
    |/  
    * afe16ae Todo arriba..
    * 7c9cc50 Mi primer Commit
    ```

    - Borramos la rama (opcional)
    ```
    git branch -d NOMBRERAMA
    ```


Tutoriales de ayuda:
- [a-successful-git-branching-model](https://nvie.com/posts/a-successful-git-branching-model/)
- [Git-Branching-Basic-Branching-and-Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [git-branch | javatpoint](https://www.javatpoint.com/git-branch)
- [using-branches| Atlassian](https://www.atlassian.com/git/tutorials/using-branches)

<br>
<br>


# 📌 Instalación

<br>

### En Mac desde la terminal
*Deberás tener previamente instalado [Homebrew](https://brew.sh/)*

```
 brew install git
```

<br>

### En Linux desde la terminal (Debian/Ubuntu)

```
apt-get install git
```
<br>

### En Windows [descargando el ejecutable desde aquí](https://git-scm.com/download/win)

<br>
<br>
<br>

# La terminal

<br>

Para trabajar con **Git** debemos utilizar nuestra **terminal** o consola.

La terminal es un software que te permite dar **instrucciones** a tu ordenador por medio de **líneas de comando**.

<br>

📌 <span style="text-decoration:underline; font-weight: bold; font-size: 20px">Lista de comandos básicos de la terminal</span>

<br>

Lista todos los `archivos y carpetas` dentro el diretorio actual
```
ls
```

<br>

Lista todos los `archivos y carpetas` dentro del directorio actual incluyendo los archivos ocultos

```
ls -a
```

<br>

Para `ingresar a una carpeta` determinada. 

```
cd <nombre-de-la-carpeta>
```

<br>

Para `salir de la carpeta actual` (moverse una carpeta hacia atrás)

```
cd ..
```

<br>

Para `volver a la ruta de origen` por defecto de la terminal

```
cd
```

<br>

`Imprime la ruta` del directorio donde estamos actualmente

```
pwd
```

<br>

Para `limpiar la pantalla`
```
clear
```

<br>
<br>
<br>

# Comandos básicos de Git

<br>


📌 <span style="text-decoration:underline; font-weight: bold; font-size: 20px">Lista de comandos básicos de Git</span>

<br>

Para comprobar que tenemos instalado Git y `ver la versión`.

```
git --version
```

<br>

Para ingresar el `nombre de usuario`.
```
git config --global user.name <nombre-de-usuario-en-github>
```

<br>

Para ingresar el `email del usuario`.
```
git config --global user.email <tu@email.com>
```

<br>

Para `verificar` cuál es el nombre de usuario que tenemos `configurado`.

```
git config --global user.name
```

<br>

Para ver la `configuración actual`.
```
git config --list
``` 

<br>

Para `clonar` (hacer una copia) de tu repositorio de GitHub en local.

```
git clone <url-del-repo-que-quieres-clonar> <nombre-alternativo-para-carpeta-local> (opcional)
``` 

<br>

Para `añadir al staging area` uno o más ficheros determinados.
```
git add <nombre-del-fichero>
```

<br>

Para `añadir al staging area` todos los ficheros que han sufrido modificaciones.
```
git add -A` o `git add .
```

<br>

Para realizar un `commit` y agregar un mensaje que lo identifique.
```
git commit -m "<tu-mensaje>"
``` 

<br>

Para `subir los cambios` al repositorio en remoto (GitHub)
```
git push
``` 

<br>

Para `descargar los cambios` que estén en remoto y no tenga en mi ordenador
```
git pull
```
<br>

Para ver el `historial de todos los commits` realizados en ese repositorio

```
git log
```

<br>
<br>


---
---

<br>

# 🗒️ Material extra

<br>

- 😻 [Te lo explico con gatitos](https://teloexplicocongatitos.com/poster/tlecg04) 

- ⏯️ [Taller de Introducción a Git](https://www.youtube.com/watch?v=Mkd8idNUolM)

- 🎮 [Learn Git Branching Game](https://learngitbranching.js.org/)

- 💻 [Sitio oficial de Git](https://git-scm.com/)
- 💻 [Git/GitHub Cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)

<br>
<br>

---
---

<br>
<br>

![img](../assets/ejercicio/git-merge.gif)







