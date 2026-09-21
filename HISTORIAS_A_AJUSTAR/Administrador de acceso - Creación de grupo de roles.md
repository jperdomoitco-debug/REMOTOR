

| Creación de grupo de roles |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación de grupo de roles |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Agrupar un conjunto de roles bajo un solo nombre representativo (Ej. 'Paquete Gerencia' o 'Auditores') para facilitar asignaciones masivas y reducir la carga operativa. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creación de grupo de roles |  |  |  |

| Situación Actual |
| :---- |
| No existe el concepto de agrupación de permisos en el negocio. |

| Situación Deseada |
| :---- |
| Reducir el tiempo administrativo y posibles errores humanos al no tener que buscar y asignar 5 roles distintos uno por uno cada vez que ingresa un usuario directivo. |

**HU\_001 Crear grupo de roles**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Crear grupo de roles** | **Dado que:**  El administrador de acceso está en el módulo de **grupos de accesos** y selecciona **crear grupo**. **Cuando:**  Ingresa el nombre del grupo **C-Level**, selecciona las casillas de los roles: facturador, almacenista y  coordinador administrativo y pulsa guardar. **Entonces:**  Se crea a nivel lógico un  **grupo**  conteniendo las referencias a esos 4 roles, dejándolo disponible para futuras asignaciones a usuarios. |

