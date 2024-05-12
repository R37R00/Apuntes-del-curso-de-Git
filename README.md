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