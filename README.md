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
