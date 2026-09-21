

| Consultar cortes de prefactura |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar cortes de prefactura |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Facturador |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Consultar todos los cortes de prefactura generados en el sistema, lo cual permitiría habilitar una vista de listado para facilitar el seguimiento de los ciclos de cobro y la re-descarga o revisión de los reportes históricos asociados a cada corte. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Facturación  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar cortes de prefactura |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, al depender de scripts o matrices manuales en Excel, no existe un repositorio centralizado que permita consultar, auditar o listar los cortes de facturación generados previamente para los distintos clientes. No cuenta con una interfaz para revisar el estado, las fechas o las órdenes de trabajo incluidas en cortes de facturación pasados, solamente se puede verificar la prefactura ya sea de manera independiente en cada archivo de control de saldos o individualmente según la entidad. |

| Situación Deseada |
| :---- |
| Habilitar una vista de listado donde se pueda consultar todos los cortes de facturación generados en el sistema. Facilitar el seguimiento de los ciclos de cobro y permitir la re-descarga o revisión de los reportes históricos asociados a cada corte.  |

**HU\_001 Listado y consulta de cortes de prefactura**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Listado y consulta de cortes de prefactura** | **Dado que:**  Se generan periódicamente cortes de facturación para las distintas entidades y se requiere mantener una trazabilidad histórica que reemplace el manejo manual de archivos. **Cuando:**  Se accede a la opción de listar cortes de prefactura en el sistema. **Entonces:** Se debe mostrar un listado o tabla con el histórico de los cortes generados (relacionando datos clave como número de corte, entidad, fecha de creación, usuario y estado), permitiendo consultar su detalle o descargar nuevamente el archivo Excel asociado. |

