

| Creación de rol |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Registro de un nuevo rol de sistema |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Crear roles o roles específicos dentro del sistema para agrupar permisos lógicos según las áreas de la empresa y aplicar el principio de mínimo privilegio. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Solicitar cotización. |  |  |  |

| Situación Actual |
| :---- |
| Todos los usuarios tienen los mismos permisos sobre las carpetas de Drive (operativo, facturación, licitaciones) exponiendo información financiera a personal netamente operativo. |

| Situación Deseada |
| :---- |
| Establecer una estructura jerárquica o por departamentos (Ej. rol Facturación, rol Licitaciones, rol Operativo) que servirá como estructura base para asignar permisos a carpetas y funcionalidades de forma granular. |

**HU\_001 Registro de un nuevo rol de sistema**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Registro de un nuevo rol de sistema** | **Dado que:** El administrador está en el módulo de "roles" y selecciona la acción "Crear rol". **Cuando:** Ingresa el nombre del rol, una descripción de las funciones que abarca, y lo guarda. **Entonces:** El sistema almacena el rol en el catálogo de roles, asignándole un identificador único y dejándolo disponible (estado Activo) para ser configurado o asignado. Los campos mínimos requeridos son:  Nombre del rol Descripción detallada del rol Estado por defecto (Activo). |

