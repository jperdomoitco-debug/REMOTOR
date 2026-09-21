

| Consultar oferta económica |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Búsqueda de procedimientos y precios por contrato |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtro dinámico en la maestra de procedimientos |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Consulta y filtro multicriterio de vehículos |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Consultar y filtrar la oferta económica, vehículos y procedimientos desde el sistema mediante múltiples criterios de búsqueda (por contrato, placa, sigla, procedimiento o ítem), para agilizar la búsqueda de tarifas y la creación de órdenes de trabajo sin recurrir a archivos manuales. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Solicitar cotización. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, la gestión de la Oferta Económica (OE) se realiza mediante múltiples archivos de Excel aislados, uno por cada licitación. Esto genera dispersión de información, redundancia de datos y un alto riesgo operativo al carecer de una única fuente de verdad. El proceso es manual, ineficiente y propenso a errores al requerir rellenar campos repetidamente. Para verificar los precios o la oferta económica aplicable a un vehículo, el operador debe buscar manualmente dentro del archivo Excel ("control de saldos"). Esto implica filtrar celdas a mano, buscar la columna correcta de repuestos o mano de obra (con o sin IVA) y validar que corresponda a las características del vehículo, lo que genera demoras e inconvenientes en la operación diaria. |

| Situación Deseada |
| :---- |
| Centralizar la Oferta Económica en una solución digital tipo formulario con capacidad de consulta filtrada (por Entidad, Contrato y Vehículo). Esto permitirá optimizar el proceso, garantizando el acceso a precios actualizados, reduciendo el tiempo operativo y asegurando una gestión basada en datos consistentes. También cuenta con un buscador centralizado que permite filtrar rápidamente por contrato, vehículo (placa, sigla, marca, CC) y/o procedimiento. El sistema debe listar de forma clara y dinámica los procedimientos disponibles con sus valores actualizados de mano de obra y repuestos (con y sin IVA) según el contrato seleccionado, facilitando la creación de órdenes de trabajo de forma precisa. |

**HU\_001 Búsqueda de procedimientos y precios por contrato**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Búsqueda de procedimientos y precios por contrato** | **Dado que:** Se necesita consultar la oferta económica aplicable a una entidad **Cuando:**  Selecciona un contrato específico o ingresa la placa de un vehículo asociado **Entonces:** El sistema muestra la lista de procedimientos vigentes para ese contrato, desplegando los valores de repuesto y mano de obra (con y sin IVA). |

**HU\_002 Filtro dinámico en la maestra de procedimientos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtro dinámico en la maestra de procedimientos** | **Dado que:** Se está visualizando la oferta económica de un contrato **Cuando:** Se  ingresa una palabra clave en el buscador (ej. "alternador", "freno", "aceite") o el número de ítem **Entonces:** El sistema filtra en tiempo real la lista de procedimientos mostrando únicamente las coincidencias y sus respectivos costos. |

**HU\_003 Consulta y filtro multicriterio de vehículos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consulta y filtro multicriterio de vehículos** | **Dado que:** Se requiere verificar la ficha y asignación de un vehículo **Cuando:** Se realiza una búsqueda filtrando por placa, sigla, marca o cilindraje (CC) **Entonces:** El sistema muestra los vehículos coincidentes y detalla los diferentes contratos a los que está vinculado actualmente. |

