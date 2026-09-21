

| Consultar contratos |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consulta y listado general de la maestra de contratos |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtrado y búsqueda avanzada de contratos |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar contratos |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, al no existir una maestra centralizada de contratos, la consulta de la información contractual y sus ofertas económicas se realiza navegando manualmente a través de carpetas individuales en Google Drive y buscando dentro de archivos Excel dispersos "Control de saldos". No es posible realizar consultas estructuradas por parámetros clave (como número de contrato, proceso, entidad o tipo de contratación), lo que retrasa la toma de decisiones y dificulta la auditoría operativa. |

| Situación Deseada |
| :---- |
| Implementar una interfaz de consulta estandarizada que permita buscar y visualizar de forma rápida todos los contratos registrados en el sistema, sirviendo como la fuente de verdad y dependencia para la ejecución y parametrización posterior. Facilitar la localización de la información contractual mediante filtros basados en los datos esenciales de los pliegos y de los involucrados. |

**HU\_001 Consulta y listado general de la maestra de contratos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consulta y listado general de la maestra de contratos** | **Dado que:** Se cuenta con una maestra centralizada de contratos para unificar la información que anteriormente se gestiona en carpetas de Drive.  **Cuando:** La gerencia operativa requiera consultar el listado general de contratos registrados en el sistema. **Entonces:** Se debe mostrar una interfaz de consulta estructurada (tabla) que relacione los datos clave del contrato:  número de contrato número de proceso objeto tipo de contratación entidad contratante  NIT  supervisor. |

**HU\_002 Filtrado y búsqueda avanzada de contratos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtrado y búsqueda avanzada de contratos** | **Dado que:** Se requiere agilizar la localización de contratos específicos dentro del repositorio centralizado para su posterior parametrización y gestión operativa. **Cuando:** La gerencia operativa aplique criterios de búsqueda o filtros por número de contrato, número de proceso, entidad contratante o tipo de contratación. **Entonces:** Se debe filtrar dinámicamente los registros y mostrar el detalle correspondiente a la selección realizada. |

