

| Consultar órdenes de trabajo aprobadas |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Listar OT aprobadas |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Consultar el cuadro de actividades autorizadas |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Jefe de taller |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Consultar las órdenes de trabajo en estado aprobado, con su cuadro de actividades autorizadas, para priorizar y planificar la asignación de técnicos e iniciar la ejecución. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Taller |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consulta de OT aprobadas para el jefe de taller. |  |  |  |

| Situación Actual |
| :---- |
| El jefe de taller conoce las ordenes de trabajo aprobadas de forma verbal consultando a la coordinación administrativa, esta le dice que ítems o procedimientos ha sido aprobado por supervisor de la entidad |

| Situación Deseada |
| :---- |
| Se desea que tenga acceso a un listado de ordenes de trabajo en estado aprobado con filtros (contrato, placa, fecha) y acceso al cuadro de actividades autorizadas desde cada orden de trabajo. |

**HU\_001 Listar OT aprobadas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Listar OT aprobadas** | **Dado que:**  El supervisor de la entidad ha aprobado elementos en la orden de trabajo **Cuando:** Se consulta el listado **Entonces:** se muestra el listado de las ordenes de trabajo aprobadas con filtros por contrato, placa, sigla y fecha. |

**HU\_002 Consultar el cuadro de actividades autorizadas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Consultar el cuadro de actividades autorizadas** | **Dado que:** La coordinación administrativa notifica que una orden de trabajo o los ítems ya han sido aprobado por la entidad. **Cuando:** Se consulta la orden de trabajo para validar las actividades autorizadas **Entonces: Se** puede ver el cuadro de actividades autorizadas y los ítems aprobados para iniciar la ejecución. |

