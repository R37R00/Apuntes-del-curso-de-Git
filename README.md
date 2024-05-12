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