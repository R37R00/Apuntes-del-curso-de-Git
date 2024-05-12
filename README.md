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