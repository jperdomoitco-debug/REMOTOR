

| Consultar sucursales |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consulta y Listado General de Sucursales y Satélites |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtrado y Consulta Detallada por Jerarquía |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar sucursales |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, al no existir una maestra formal de sucursales o satélites, la ubicación de la operación y sus puntos de apoyo se manejan de forma aislada o estática. No es posible consultar de manera rápida qué talleres satélites o unidades de outsourcing dependen de una sucursal principal específica por ciudad, lo que dificulta la auditoría y el control operativo. |

| Situación Deseada |
| :---- |
| Implementar la  consulta centralizada que permita listar, buscar y filtrar todas las sucursales y satélites registrados en el sistema. El objetivo principal es poder consultar el detalle de una sede visualizando claramente su clasificación (principal/satélite) y su dependencia estructural |

**HU\_001 Consulta y Listado General de Sucursales y Satélites**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Título de historia de usuario** | **Dado que:** Se cuenta con una maestra centralizada de sucursales y satélites para soportar la expansión a nivel nacional. **Cuando:** La gerencia operativa requiere consultar el listado general de ubicaciones operativas registradas en el sistema. **Entonces:** Se debe mostrar una interfaz de consulta/tabla que relacione los datos clave de cada sede:  nombre tipo (Principal o Satélite) ciudad dirección responsable a cargo. |

**HU\_002 Filtrado y Consulta Detallada por Jerarquía**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Título de historia de usuario** | **Dado que:**  Se requiere mantener trazabilidad sobre los puntos de apoyo operativo y su vinculación geográfica según los lineamientos de control de configuraciones. **Cuando:** La gerencia operativa aplique filtros de búsqueda por ciudad, tipo de sede o sucursal principal asociada. **Entonces:** Se debe permitir filtrar dinámicamente los resultados y, al consultar el detalle de una sucursal principal, listar de forma anidada o relacionada las unidades satélites (talleres pequeños, servitecas o terceros) que dependen de ella. |

