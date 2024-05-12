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