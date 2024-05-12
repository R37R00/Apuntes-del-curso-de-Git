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