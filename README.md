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