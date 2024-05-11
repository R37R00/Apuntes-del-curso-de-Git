# Apuntes del curso de Git
Este repositorio está dedicado a los apuntes del curso de Git dictado por la SCESI.

## CLASE 1
### Crear un proyecto
#### Sintaxis de un comando de Git: *Git* (comando) parámetro
Para la creación de un proyecto se tienen los siguientes comandos: 


 #### \* Comando:
- **git init (nombre del proyecto)**: Crea un repositorio de manera local.

**Nota:** Al ejecutar el comando se crea una carpeta oculta llamada *.git*, que contendrá todos los elementos necesarios para iniciar el repositorio del proyecto.

Para verificar que se creó correctamente el repositorio al final del nombre de la carpeta nos deberá de aparecer la rama en la que estamos.

Ejemplo: 
**Apuntes-del-curso-de-Git *(main)***

En este caso al final pone (main), lo cual nos indica que nos encontramos en la rama principal de nuestro proyecto.

## States y Commits
Cualquier archivo que esté dentro de una carpeta que ha sido inicializado con git, pasará por los siguientes estados:
### Los 3 estados de Git
#### 1.-  Modified
Este estado corresponde cuando un archivo se ha creado, modificado o se ha eliminado.
#### 2.- Staged
Este estado es cuando un archivo está marcado para que pueda ser confirmado, este estado es transitorio.
##### 3.- Commited
Este estado es cuando el archivo se está grabado en el repositorio local(es decir un punto de guardado).

#### \* Comandos:
- **git status:** Proporciona el estado actual del repositorio.
- **git add (archivo):** Sirve para agregar cambios al directorio de trabajo.
- **git restore (archivo):** Sirve para descartar los cambios en el directorio de trabajo para el archivo especificado, volviendo al último estado del commit.
- **git resotre --staged . :** Se utiliza para deshacer la adición de todos los archivos en el directorio actual al área de preparación.
- **git add . :** Este comando agrega todos los archivos y carpetas en el directorio actual al área de preparación.

### ¿Qué es un "Commit"?
Los commits sirven para registrar los cambios que se han producido en el repositorio.

Es como el botón de "Guardar" en un juego.

### ¿Cómo hago un commit?
Primero que nada el **mensaje** para le commit es MUY IMPORTANTE.
#### \* Comandos:
- **git commit:**  Este comando crea un nuevo commit con los cambios que están en el área de preparación.
- **git commit -m "mensaje":** Este comando crea un nuevo commit y usa el texto entre las comillas como mensaje de commit.
- **git --help:** Muestra una lista de los comandos más comunes de Git en la terminal.
- **git log:** Se utiliza para mostrar el historial de commits en un repositorio Git.

### ¿Qué es el HEAD?
Se entiende al "HEAD", como un "estás aquí".
El HEAD es un puntero que te indica en dónde te encuentras

# Clase 2
## Ramas, merge y conflictos
### ¿Qué es una rama?
Una rama es una instantánea o un snapshot de la división del estado del código.

Es una bifurcación de la rama principal.
Es como tener primero una avenida principal, donde las ramas son como otras calles que salen de la avenida principal.
Es muy necesario realizar el 1er commit, para ver de dónde se realizarán más copias y bifuraciones.

### ¿Para qué sirven las ramas?
Permiten realizar un desarrollo no lineal y colaborativo.

### Creando la primera rama:
#### \*Comandos:
- **git branch:** Lista las ramas existentes.
- **git branch (nombre de la rama):** Crea una nueva rama con el nombre especificado.
- **git switch (nombre de la rama a la que se desea cambiar):** Cambia de la rama actual a la que se especificó.
- **git checkout (nombre de la rama a la que se desea cambiar):** Cambia de la rama actual a la que se especificó.

### Fusionar ramas
Cuando hablamos de fusión nos referimos a que los cambios que hemos realizado en la rama se integran en otra rama, de forma que el código que habíamos generado en la nueva rama se asimila a otra.

#### \* Comandos:
- **git merge (nombre de la rama con la que se desea fusionar la rama actual):** Fusiona los cambios de la rama especificada con la información de la rama actual.

### Eliminar ramas, ¿Por qué?
Para mantener limpio el espacio de trabajo.
Porque es una buena práctica, además que las ramas tienen un propósito único y corto de período.

#### \* Comandos:
- **git branch -d (nombre de la rama que se desea eliminar):** Elimina la rama especificada.
- **git branch -D (nombre de la rama que se desea eliminar):** Elimina la rama especificada de manera forzada.
- **git -c (nombre de la rama a la que se desea cambiar):** Al igual que el switch o el checkout, cambia a la rama especificada.
- **git log --oneline:** Muestra los títulos de los commits que se realizaron sin entrar a detalle.
- **git log --graph:** que muestra un gráfico ASCII en la terminal que representa la historia de commits del repositorio.
- **git merge header --no-ff:** Se utiliza para fusionar la rama header en tu rama actual en Git. Estás fusionando la rama header en tu rama actual y estás asegurándote de que Git cree un nuevo commit de merge en el proceso.
-- **git log --graph --oneline:** Este comando muestra la historia de commits en una línea por commit, junto con un gráfico ASCII que representa la estructura de la historia de commits.

### Conflictos en Git
Un conflicto ocurre cuando dos o más desarrolladores modifican la misma línea de código en el mismo archivo, o si un desarrollador elimina un archivo mientras otro desarrollador está modificando ese archivo. Estos conflictos suelen ocurrir cuando se intenta fusionar (merge) ramas en Git.

#### Esta es la sintaxis de un conflicto:
~~~
<<<<<<< HEAD
código de la rama actual
=======
código de la otra rama
>>>>>>> nombre-de-la-otra-rama
~~~

#### \* Comandos:
- **git merge --abort:** se utiliza para cancelar un proceso de fusión (merge) que ha resultado en conflictos. Cuando se ejecuta este comando, Git intenta volver al estado en el que te encontrabas antes de iniciar la fusión. Es importante mencionar que **git merge --abort** solo está disponible si la fusión ha resultado en conflictos. Si la fusión se completó sin conflictos, entonces no podrás utilizar **git merge --abort**.

### Resolviendo conflictos
Al resolver, debemos decidir entre:
- Nos quedamos con los cambios de la rama main.
- Nos quedamos con los cambios que vienen de la rama changes.
- Modificamos los cambios para realizar una fusión personalizada.

~~~
<<<<<<< HEAD
código de la rama actual
=======
código de la otra rama
>>>>>>> nombre-de-la-otra-rama
~~~

Arriba tenemos el contenido que ya existía.

==============

Debajo tenemos el contenido de la rama que queremos incorporar.

# Clase 3
## Repositorios remotos
### Enlazar un repositorio local con un repositorio remoto
#### Pasos:
1. Navega hasta tu perfil de GitHub
2. Navega hasta la pestaña "Repositories" en tu perfil.
3. Dar clic en el botón verde de "New", en la parte superior derecha.
4. Llenar los campos de:
- Repository Name
- Description(opcional)
5. Mantenerlo público o marcar la opción de privado dependiendo del usuario.
6. Si deseas colocar una licencia marca una de las opciones.
7. Dar clic en el botón verde de "Create repository" en la parte inferior del formulario.
8. Abre Gitbash.
9. Navega hasta la carpeta donde se encuentra tu repositorio local.
10. Escribe el siguiente comando:
#### \*Comandos:
- **git remote add origin (url del repositorio remoto):** Se utiliza para agregar un nuevo repositorio remoto a tu repositorio local de Git.
- **git remote -v:** Se utiliza para listar todos los repositorios remotos que están configurados para tu repositorio local de Git.
11. Ya tenemos nuestro repositorio local enlazado con nuetro repositorio remoto.
### Generar key SSH
#### \*Comandos:
- **ls -al ~/.ssh:** Se utiliza para listar todos los archivos y directorios en el directorio .ssh
- **ssh-keygen -t rsa -b 4096 -C "tuemail@gmail.com":**
Este comando se utiliza para generar una nueva clave SSH. Aquí te explico un poco más sobre los componentes de este comando:
- **eval "$(ssh-agent -s)":** Se utiliza para iniciar el agente SSH en tu terminal.
- **ssh-add ~/.ssh/id_rsa.pub:** Añadir key SSH.
- **clip < ~/.ssh/id_rsa.pub:** Copiar en el portapapeles.
- Pegar en la sección "Key" de GitHub que está en la parte de "Settings" de tu perfil - SSH and GPG keys
- Dar clic en el botón de "New SSH key".

### Escribiendo en el repositorio remoto
#### \*Comandos:
- **git push origin (rama a sincronizar):** Se utiliza para subir los cambios que has hecho en tu rama local a la rama correspondiente en tu repositorio remoto.

### Clonando un repositorio
#### \*Comandos:
- **git clone (url del repositorio remoto):** Se utiliza para crear una copia local de un repositorio que está alojado en un servidor remoto.
- **git push --help:** Abre la página de manual (man page) para el comando git push
- **git push --all:** Sube todas tus ramas locales a tu repositorio remoto.
- **git branch -a:** Se utiliza para listar todas las ramas en tu repositorio Git, tanto las ramas locales como las remotas.
- **git fetch:** Se utiliza para descargar datos desde un repositorio remoto. Los datos que se descargan incluyen las ramas y los commits del repositorio remoto que no están presentes en tu repositorio local.

### Elminar ramas
#### \*Comandos:
- **git remote prune origin:** Este es el comando que se utiliza para eliminar referencias a ramas remotas que ya no existen en el repositorio remoto.


# Clase 4
# Push, Pull y Pull request

#### \* Comandos:
- **git Push:** Nos sirve para empujar cualquier cambio o modificación del repositorio local al reposotiorio remoto.
Nota: Si no se especifica nada, Git intentará subir todas las ramas locales y cambios realizados de manera local al repositorio remoto.
- **git push (rama de destino):** Sube las modificaciones realizadas en la rama local a la rama especificada.
- **git push -u origin (rama a vincular):** El comando git push -u es una forma de configurar una relación entre tu rama local y una rama en el repositorio remoto. La opción -u es una abreviatura de --set-upstream. Sirve para hacerle entender a git que en un futuro cuando en un futuro al hacer el comando git push o git pull sin especificar la rama, Git sabrá que te refieres a la rama que vinculaste con este comando.
- **git push -f:** El comando git push -f es una versión forzada del comando git push. La opción -f es una abreviatura de --force.

Cuando haces git push -f origin login, por ejemplo, estás forzando a Git a empujar tus cambios a la rama login en el repositorio remoto origin, incluso si esto resulta en la pérdida de commits en el repositorio remoto.

**Nota:**
**Esto puede ser peligroso si otros están trabajando en la misma rama, ya que sus cambios pueden ser sobrescritos. Por lo tanto, se recomienda usar git push -f con precaución y generalmente solo en ramas donde eres el único que está trabajando.**

**Por ejemplo:**
Cuando haces git push -u origin login, por ejemplo, estás empujando tus cambios a la rama login en el repositorio remoto origin, y también estás configurando esa rama remota para ser la rama “upstream” o “de seguimiento” para tu rama local login.

**Esto tiene un par de ventajas:**

En el futuro, puedes simplemente hacer git push o git pull sin especificar la rama, y Git sabrá que te refieres a la rama login en origin.
Git puede darte información sobre si tu rama local está adelante, detrás o ha divergido de la rama remota.
- **git pull:** Nos sirve para jalar o descargar los cambios o modificaciones del repositorio remoto al local.

## Pull Request
Un pull request o de forma abreviada **PR**, es una petición de cambios que se envía al repositorio original de otra persona.
Por ejemplo encuentro un repositorio público muy interesante en el que quiero realizar un aporte y para avisar al dueño de ese repositorio hago un pull request para avisarle que quiero añadir cambios a su repositorio. Ya depende del dueño si acepta los cambios o no.

### ¿Cómo hacer una PR?
Tenemos que subir  nuestra rama con **git push** y a continuación hay 2 manera:
- La rama la subiste recientemente y te aparece la opción en GitHub > Code.
- Irnos al apartado de Pull Request.
### Hacer una buena PR
1. Enfocar tu código en una sola cosa.
2. Explica tu pull request.

#### \*Comandos:
- **git reflog show:** Se utiliza para mostrar un registro de todas las acciones que modificaron el puntero HEAD en tu repositorio Git. Esto incluye cosas como los commits, los cambios de rama y otros movimientos de HEAD.

### Revisar una PR
1. Proporciona siempre un feedback positivo.
2. Concreción  y claridad.
3. Entiende el contexto 

# Clase 5
## Flujos de trabajo
- ### Git Flow
Es un flujo de trabajo antiguo, utiliza las ramas:
1. **main o master:** Contiene el código de producción:
2. **develop:** Código de pre-producción que todavía tiene que ser probado y validado.
3. **Feature:** Características nuevas para el proyecto.
4. **Release:** Características nuevas para el proyecto.
5. **Hotfix:** Parches o arreglar bugs pequeños.

- ### GitHub Flow
Es un flujo de trabajo más ligero y entendible. La rama main y cualquier otra rama que quiera ser integrada por medio de una **Pull Request**

- ### Trunk Based Development
Es una estrategia de desarrollo de software en la que todos los desarrolladores realizan cambios de código en una única rama compartida, conocida como "trunk" o “línea principal”, en lugar de trabajar en ramas separadas durante períodos prolongados.
Sólo la rama main y ramas auxiliares efímeras que quieran ser integradas por medio de una pull request.

- ### Ship / Show / Ask
1. **Ship:** Se fusiona en la rama principal sin revisión.
2. **Show:** Abre una petición de cambios para ser revisado por CI, pero se fusiona inmediatamente.
3. **Ask:** Ask una PR para discutir los cambios antes de fusionarlos.

#### Reglas:
- Tener un buen sistema de CI/CD(Interacción Contínua y Despliegue Contínuo).
- Las revisiones de código no son requerimientos.
- Las ramas son lo más pequeñas posibles.
- La personas confían en el resto del equipo.

# Clase 6
# Buenas prácticas
### ¿Cada cuánto hacer un commit?
A menudo.
Es mejor hacer pequeños commits, agrupando pequeñas mejoras o acciones, que un commit con todo lo que se quiere hacer.

Pero hacer commit a menudo no significa que debas de hacer commits sin sentido.

### Escribir buenos commits
- Usar el verbo imperativo (Add, change, fix, remove).
- No uses el punto final ni putos suspensivos en tus mensajes(a lo mucho una coma).
- Usar como máximo 50 caracteres para tu mensaje del commit.
- Añade todo el contexto que sea necesario en el cuerpo del commit, utilizando reglas de puntuación.
- Utilizar prefijos para que el mensaje de commit sea más semántico.
#### Prefijos:
- **feat:** para una nueva característica para el usuario.
- **fix:** para un bug que afecta al usuario.
- **perf:** para cambios que mejoran el rendimiento del sitio.
- **build:** para cambios en el sistema de build, tareas de despliegue o instalación.
- **ci:** para cambios en la integración continua.
- **docs:** para cambios en la documentación.
- **refactor:** para refactorización del código como cambios de nombre de
variables o funciones.
- **style:** para cambios de formato, tabulaciones, espacios o puntos y coma, etc;
no
afectan al usuario.
- **test:** para tests o refactorización de uno ya existente.

#### \*Comando:
- **git switch -c:** Se utiliza para crear una nueva rama y cambiar a ella en un solo paso. La opción -c es una abreviatura de --create, que indica a Git que debe crear la rama si aún no existe.

# Clase 7
### ¿En qué caso deshacemos cambios?
- Dejó de funcionar el proyecto.
- Queremos recuperar una parte del código que eliminamos.
- Queremos recuperar archivos que eliminamos.

## Comandos destructivos y no destructivos
Los comandos destructivos afectan el historial de commits realizado, sin embargo los comandos no destructivos trabajan en base al historial sin afectarlo.

#### \*Comandos destructivos(Usarlos con preacaución y cuando se sabe totalmente lo que se hace)
- **git reset:** Posee dos opciones:
* **soft:** Mantiene los cambios que ocurrieron antes de hacer un commit. Nos permite deshacer cambios volviendo al punto que le indiquemos con la posibilidad de volver a puntos futuros.
* **hard:** De la misma manera que el soft sólo que en este caso ya no se nos permite volver a las versiones futuras.

**Ejemplo:** 
- **git reset --hard (hash del commit a retornar)**

**Nota:** También se le pueden pasar el parámetro de cuántos commits queremos retroceder a partir del HEAD:
**git reset --soft HEAD~4:** Retrocede 4 commits despues del HEAD.

## Comandos no destructivos
- **git revert:** Revierte los cambios en base a los commits que se introdujeron, no borra el historial, sino que agrega un nuevo commit con los cambios revertidos.
**Ejemplo:** 
- **git revert HEAD ~5:** Crea un nuevo comando que deshace los cambios realizados en el quinto commit anterior al HEAD.

- **git checkout:** Nos permite recuperar código específico de commits.

**Extendiéndonos con el comando git checkout:**

El comando git checkout no es destructivo en sí mismo, pero puede sobrescribir cambios locales no guardados, por lo que se debe usar con cuidado.

El comando git checkout se utiliza principalmente para dos cosas:

- **Cambiar entre ramas o commits:** Puedes usar git checkout seguido del nombre de una rama para cambiar a esa rama. También puedes usar git checkout seguido de un hash de commit para mover tu HEAD a ese commit específico. Ejemplo para cambiar a una rama:

#### \*Comandos:
- **git checkout nombre-de-la-rama**
- **git checkout (hash del commit)**.
- **git checkout nombre-del-archivo:** Este comando nos sirve para revertir el archivo que especificamos al último commit que hicimos.

# Clase 7(Última clase de Git)
# Hooks, Alias y trucos en Git
## ¿Qué es un Hook?

- Un hook o punto de enganche, es la posibilidad de ejecutar una acción o script cada vez que ocurre un evente determinado en Git.
- Los hooks en sirven para personalizar el comportamiento de Git y automatizar tareas en ciertos puntos del flujo de trabajo de desarrollo.
- Hooks del lado del clietnte.
- Hooks del lado del servidor.

## Hooks del lado del cliente
Sólo afecta al repositorio local que los contiene.
#### \*Principales tipos de hooks:
- **pre-commit:** Son acciones o scripts que se ejecutan antes de realizar un commit.
- **prepare-commit-msg:** Sirve para modificar el mensaje del commit o añadir cualquer información extra.
- **commit-msg:** Es el sitio perfecto para hacer todas las comprobaciones pertinentes al mensaje.
- **post-commit:** Se ejecuta después de que se ha hecho un commit. Puede ser útil para notificar a otros servicios o usuarios sobre el nuevo commit.
- **pre-push:** Antes de sincronizar con el repositorio remoto.
- **post-checkout:** Se ejecuta después de que se ha hecho un checkout. Puede ser útil para configurar el entorno de trabajo en función de la rama actual.
- **post-merge:** Se ejecuta después de que una fusión (merge) ha sido realizada con éxito.

## Hooks del lado del servidor
- **pre-receive:** Se ejecuta cada vez que se recibe un push en el servidor antes de que se actualice cualquier referencia.
- **update:** Se ejecuta para cada rama que se está actualizando en un push.
- **post-receive:** Se ejecuta después de que todas las referencias se han actualizado en un push. 

### Creando mi primer hook
Para crear un propio hook sólo tienes que crear un archivo
nombre-del-hook en la carpeta .git/hooks y en él poner el
código que quieras que se ejecute. Puedes usar todo tipo de
intérpretes de lenguaje de programación como bash, node,
python, perl, etc.

### ¿Qué es un Alias?
Permiten definir una serie de comandos que pueden ser usados en lugar de nombres completos. Convertir algo largo en algo corto.

#### \*Comando para crear un alias
- **git config --global alias.(nombre del alias) "Comando a ejecutar"**
**Ejemplo:**
git config --global alias.wo log --oneline

- **git config --global --unset alias.(nombre del alias):** Eliminar el alias creado.

### Trucos en Git
#### \*Comandos:
#### Guardar tus cambios temporalmente
- **stash**
- **stash -u**
- **stash pop**

#### Aplicar cambios de commits en específico
- **git cherry-pick (hash)**

#### Detectar qué commit es el que ha introducido un bug
- **git bisect**
- **git bisect start**
- **git bisect bad**
- **git bisect good**
- **git bisect reset**

#### Cambiar el nombre de un commit
- **git commit --amend -m (descripción del commit)**

#### Recupera un archivoen concreto de otra rama o commit
- **git checkout (hash) (archivo)**