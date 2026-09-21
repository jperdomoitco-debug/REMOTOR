

| Modificar / Eliminar rol |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Modificar / Eliminar rol |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Editar el nombre o descripción de un rol existente para adaptarlo a cambios organizacionales, o eliminarlo si el rol ya no es válido, manteniendo la coherencia de los accesos. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Modificar / Eliminar rol |  |  |  |

| Situación Actual |
| :---- |
| No existe gestión de roles ni políticas de acceso estructuradas. |

| Situación Deseada |
| :---- |
| Poder gestionar el ciclo de vida completo de los roles creados en el sistema, asegurando que no queden roles huérfanos o usuarios sin permisos válidos al eliminar un rol. |

**HU\_001 Modificar / Eliminar rol**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Actualización de metadatos de un rol** | **Dado que:**  El administrador de acceso busca un rol existente en la grilla y selecciona 'Modificar'. **Cuando:**  Cambia el nombre o la descripción del rol para ampliar su contexto y guarda los cambios. **Entonces:**  Se actualiza el registro sin afectar los permisos técnicos ya asociados ni a los usuarios que lo poseen actualmente. |
| **2** | **Eliminación segura de un rol obsoleto** | **Dado que:**  El administrador selecciona un rol que NO tiene ningún usuario vinculado actualmente  **Cuando:**  Confirma la acción irreversible en el cuadro de diálogo. **Entonces:**  Se elimina el rol de forma definitiva del listado de roles importante: Esta eliminacion puede ser lógica o definitiva |

