

| Asignar grupo a usuario |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Asignar grupo a usuario |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Vincular un grupo de roles completo a un usuario mediante una sola acción, aplicando múltiples roles al instante. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Asignar grupo a usuario |  |  |  |

| Situación Actual |
| :---- |
| Actualmente no se realiza, hay un acceso global una carpeta en Google Drive |

| Situación Deseada |
| :---- |
| Simplificar el proceso de onboarding de usuarios con roles que requieren accesos transversales otro rol o funcionalidad del sistema |

**HU\_001 Asignar grupo a usuario**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Asignar grupo a usuario** | **Dado que:** El administrador de acceso está configurando los accesos iniciales para un nuevo gerente general. **Cuando:**  En lugar de asignar roles individuales, busca en la pestaña **grupos**, selecciona **C-Level**  y lo asigna al usuario. **Entonces:**  El sistema desempaqueta internamente el grupo y le asocia al usuario todos los roles contenidos en él. Si el grupo **C-Level** contenía 4 roles, el usuario adquiere inmediatamente la sumatoria de los permisos de esos 4 roles. |

