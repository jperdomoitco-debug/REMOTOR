

| Asignar varios roles |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Asignar varios roles |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Otorgar más de un rol a un mismo usuario que cumple múltiples funciones o apoya transversalmente diferentes áreas operativas de la empresa. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Asignar varios roles |  |  |  |

| Situación Actual |
| :---- |
| La falta de segmentación actual hace que este caso no exista en el Drive. |

| Situación Deseada |
| :---- |
| Ofrecer flexibilidad técnica  como una matriz de roles  para que, si un usuario líder apoya tanto en la ejecución Operativa como en la Facturación, pueda tener ambos roles asignados de forma simultánea. |

**HU\_001 Asignar varios roles**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Acumulación de permisos de múltiples roles (Política inclusiva)**  | **Dado que:**  El administrador de acceso gestiona un usuario que ya cuenta con un rol inicial asignado en el sistema. **Cuando:**  Le asigna adicionalmente el rol **facturación** (que permite ver ofertas económicas y control de saldos). **Entonces:**  El sistema registra ambos roles para el usuario. El motor de autorización calculará los permisos como una UNIÓN lógica (Coordinador administrativo \-  Facturación), permitiéndole visualizar, usar y/o interactuar con los roles asignados |

