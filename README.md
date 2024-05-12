# Clase 8(Última clase de Git)
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