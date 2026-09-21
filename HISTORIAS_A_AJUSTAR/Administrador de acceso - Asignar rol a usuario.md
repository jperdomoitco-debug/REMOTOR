

| Asignar rol a usuario |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Vinculación individual de un rol |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Remoción de un rol específico |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Vincular un rol  previamente configurado a un usuario específico para habilitar sus capacidades de navegación dentro del sistema. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Asignar rol a usuario |  |  |  |

| Situación Actual |
| :---- |
| No hay asociación de roles por usuario; el acceso es igual para todos los roles |

| Situación Deseada |
| :---- |
| Que cada usuario tenga los accesos estrictamente necesarios correspondientes a su cargo, asignándole el rol pertinente desde su ficha de gestión. |

**HU\_001 Vinculación individual de un rol**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Vinculación individual de un rol** | **Dado que:**  El administrador se encuentra en el módulo de gestión del usuario.. **Cuando:**  Selecciona el rol desde un menú desplegable y haga clic en 'Asignar'. **Entonces:**  Se crea la relación usuario-rol. A partir de su próximo inicio de sesión, el usuario heredará los permisos de lectura o escritura definidos para la funcionalidad asignada. |

**HU\_002 Remoción de un rol específico**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Remoción de un rol específico** | **Dado que:**  El administrador revisa los roles actuales de un usuario. **Cuando:**  se hace clic en la opción 'Remover' junto al rol asignado. **Entonces:**  Se elimina la asociación y revoca inmediatamente esos permisos del usuario. |

