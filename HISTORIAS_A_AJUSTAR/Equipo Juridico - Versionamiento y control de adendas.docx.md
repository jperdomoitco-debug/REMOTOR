

| Versionamiento y control de adendas |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Transición de fases y registro de adendas |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Validación manual de adendas por autoridad de cambios |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Equipo juridico |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Guardar un historial si el pliego cambia de borrador a definitivo o si se emiten adendas, protegiendo el trabajo adelantado mediante clonación y exigiendo una autorización formal. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Licitaciones |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Versionamiento y control de adendas |  |  |  |

| Situación Actual |
| :---- |
| Cuando cambian las reglas, el equipo sobrescribe el excel manual y se pierde el rastro de lo que pedían antes. |

| Situación Deseada |
| :---- |
| Un módulo que clone el checklist actual en una nueva versión pendiente de revisión, exigiendo validación manual del equipo jurídico. |

**HU\_001 Transición de fases y registro de adendas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Transición de fases y registro de adendas** | **Dado que:** la entidad pública publicó un documento definitivo o una adenda en la plataforma secop ii  Cuando: Se indica en el sistema que hay una nueva versión del pliego y se sube el archivo pdf al drive **Entonces:** Se congela la matriz anterior en modo de solo lectura y entrega una copia exacta en estado de revisión y ajustes pendientes. Información detallada solicitada: Identificador de la acción o versión (borrador \-\> definitivo \-\> adenda 1, adenda 2, etc.)   Ajuste manual de fechas del cronograma afectado en la plataforma  |

**HU\_002 Validación manual de adendas por autoridad de cambios**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Validación manual de adendas por autoridad de cambios** | **Dado que:** La nueva versión clonada se encuentra pendiente de revisión **Cuando:** el equipo jurídico (actuando como autoridad de cambios) revisa los cambios introducidos por la entidad y registra su aprobación en el sistema **Entonces:** Se libera la versión activa, actualiza los temporizadores de cuenta regresiva y notifica a las áreas involucradas. Información detallada solicitada al usuario: Confirmación de revisión de cambios regulatorios o técnicos  Aprobación formal y firma del responsable jurídico   Regla de negocio: Ninguna adenda publicada por la entidad puede aplicarse a la operación interna sin la revisión y el visto bueno manual del equipo jurídico. |

 

