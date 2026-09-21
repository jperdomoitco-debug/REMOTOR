

| Buscar \- Modificar / Eliminar usuario |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Búsqueda y listado de usuarios |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Modificar usuario |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Eliminar usuario |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Actualizar la información de los usuarios existentes o cambiar su estado a inactivo (desactivarlos) si son desvinculados de la compañía para renovarles el acceso inmediatamente. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Modificar / Eliminar usuario |  |  |  |

| Situación Actual |
| :---- |
| No hay gestión individual de usuarios; si alguien se va de la empresa, la única solución es cambiar la configuración general de los accesos del drive pero este cambio seria es global, también se puede proporcionar permisos por carpetas en específicas pero se crea una carga operativa de gestión.  |

| Situación Deseada |
| :---- |
| Poder buscar un usuario específico por nombre o correo, modificar sus datos personales en caso de cambios de área, o inactivarlo con un clic asegurando la protección de los datos contractuales. |

**HU\_001 Búsqueda y listado de usuarios**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Búsqueda y listado de usuarios** | **Dado que:** El administrador necesita localizar un usuario. **Cuando:** Escribe nombre o correo en la barra de búsqueda o aplica filtros (estado, cargo, rol). **Entonces:** El sistema filtra en tiempo real el listado de usuarios y permite ver los roles asignados. |

**HU\_002 Modificar usuario**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Modificar usuario** | **Dado que:**  El Administrador de acceso busca a un usuario existente mediante la barra de búsqueda y selecciona 'Editar'. **Cuando:**  Se modifique un campo  **Entonces:**  Se debe actualizar el registro en la base de datos conservando el historial de sus permisos. los campos a actualizar son: Nombres completos Apellidos completos Correo electrónico corporativo Número de documento Cargo o Área |

**HU\_003 Eliminar usuario**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Eliminar usuario** | **Dado que:**  Un colaborador se retira de la compañía y el Administrador de acceso selecciona la opción 'Inactivar / Cambiar Estado' sobre su registro, esto para no perder la data relacionada a ese usuario **Cuando:**  Confirma el cambio de estado de 'Activo' a 'Inactivo'. **Entonces:**  Se debe actualizar el estado (eliminación lógica para no perder la trazabilidad de sus acciones pasadas). Importante: Se debe invalidar la sesiones activas si el usuario se elimina |

