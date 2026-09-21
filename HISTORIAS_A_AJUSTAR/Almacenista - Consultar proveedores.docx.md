

| Consultar proveedores |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar proveedores. |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Almacenista |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Se desea disponer de una fuente única de verdad para consultar información de proveedores e ítems, eliminando la dispersión actual de datos y los procesos manuales redundantes, con el fin de validar su viabilidad de manera ágil y tomar decisiones de compra confiables antes de iniciar cualquier gestión entre ellas la generación de cotizaciones. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Compras |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar proveedores. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, la consulta de proveedores e ítems depende de registros dispersos y procesos manuales, lo que obliga al almacenista a realizar búsquedas redundantes y verificaciones repetitivas para cada solicitud. Esta falta de visibilidad centralizada genera retrabajos, aumenta el riesgo de gestionar proveedores no aptos y consume tiempo operativo valioso que podría dedicarse a la toma de decisiones estratégicas. |

| Situación Deseada |
| :---- |
| Implementar un centro de consulta y validación rápida que sirva como "Fuente Única de Verdad". Este módulo debe permitir filtrar proveedores e ítems por estado y capacidad antes de iniciar la solicitud de cotización (RFQ). El objetivo es transformar la consulta en un paso de valor que valide la viabilidad del proveedor, eliminando el desperdicio operativo y asegurando que los procesos de compra comiencen solo con información confiable y estructurada. |

**HU\_001 Consultar proveedores**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar proveedores** | **Dado que:** Se requiere consultar detalles de cada proveedor, por ejemplo: datos de contacto, ítems que provee, estado del proveedor, etc. **Cuando:** Se necesite consultar datos del proveedor. **Entonces:** Desde la tabla de maestra de proveedores se permitirá consultar la información el detalle de cada proveedor. **Dado que:** el almacenista busca un ítem específico **Cuando:** realice la búsqueda por ítem, **Entonces:** debe ver qué proveedores lo suministran para comparar y elegir la mejor opción disponible en el momento. |

