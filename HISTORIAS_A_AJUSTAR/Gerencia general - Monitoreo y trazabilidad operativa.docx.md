

| Monitoreo y trazabilidad operativa |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar estados de vehículos en desarrollo y trazabilidad operativa |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Consulta y listado general de sucursales y satélites |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Filtrado y consulta detallada por jerarquía |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia general |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Disponer de un módulo centralizado que permita a la gerencia visualizar en tiempo real en qué etapa se encuentra cada vehículo con una orden de trabajo activa, así como consultar el historial detallado de su paso por el taller, asegurando que se cumplan los procesos y se diligencien los formularios requeridos por las entidades. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Financiero |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Monitoreo y trazabilidad operativa de vehículos |  |  |  |

| Situación Actual |
| :---- |
| Actualmente no existe una herramienta o manera formal en el sistema donde la gerencia pueda consultar de forma centralizada el estado de los vehículos en desarrollo, ni llevar un seguimiento de la trazabilidad a lo largo de su ciclo de servicio en el taller. |

| Situación Deseada |
| :---- |
| Disponer de un módulo centralizado que permita a la gerencia visualizar en tiempo real en qué etapa se encuentra cada vehículo con una orden de trabajo activa, así como consultar el historial detallado de su paso por el taller incluyendo su respectivo diagnóstico, asegurando que se cumplan los procesos definidos. |

**HU\_001 Consultar estados de vehículos en desarrollo y trazabilidad operativa**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar estados de vehículos en desarrollo y trazabilidad operativa** | **Dado que:** El Gerente General necesita monitorear el flujo de trabajo en el taller y verificar el cumplimiento de los procesos operativos. **Cuando:** Se consulte el listado de vehículos en desarrollo en el sistema. **Entonces**: Se debe mostrar el estado actual de las órdenes de trabajo activas y detallar la trazabilidad completa de cada vehículo (incluyendo recepción, diagnóstico, estado de aprobación de la OT, salida y los formularios correspondientes de entrada/salida diligenciados según la entidad). |

**HU\_002 Consulta y listado general de sucursales y satélites**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consulta y listado general de sucursales y satélites** | **Dado que:** Se cuenta con una maestra centralizada de sucursales y satélites para soportar la expansión a nivel nacional. **Cuando:** La gerencia operativa requiere consultar el listado general de ubicaciones operativas registradas en el sistema. **Entonces:** Se debe mostrar una interfaz de consulta/tabla que relacione los datos clave de cada sede: ●   	nombre ●   	tipo (Principal o Satélite) ●   	ciudad ●   	dirección ●   	responsable a cargo. |

 

**HU\_003 Filtrado y consulta detallada por jerarquía**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtrado y consulta detallada por jerarquía** | **Dado que:**  Se requiere mantener trazabilidad sobre los puntos de apoyo operativo y su vinculación geográfica según los lineamientos de control de configuraciones. **Cuando:** La gerencia operativa aplique filtros de búsqueda por ciudad, tipo de sede o sucursal principal asociada. **Entonces:** Se debe permitir filtrar dinámicamente los resultados y, al consultar el detalle de una sucursal principal, listar de forma anidada o relacionada las unidades satélites (talleres pequeños, servitecas o terceros) que dependen de ella. |

 

