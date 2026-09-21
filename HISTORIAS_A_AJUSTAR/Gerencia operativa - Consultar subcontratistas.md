

| Consultar subcontratistas |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consulta general de subcontratistas |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtrado y Búsqueda Avanzada de Subcontratistas |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar subcontratistas |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, los terceros o empresas utilizadas bajo la modalidad de outsourcing se gestionan de forma manual mediante rangos en archivos de Excel de control de saldos, lo que impide una consulta centralizada y estructurada. No existe una interfaz digital o repositorio central para buscar, listar o verificar el historial y los datos clave de los subcontratistas, lo que dificulta la trazabilidad al momento de validarlos para las licitaciones u órdenes de trabajo. |

| Situación Deseada |
| :---- |
| Implementar una interfaz de consulta y listado que permita a los usuarios visualizar de forma clara todas las empresas o terceros registrados en la maestra de subcontratistas. Habilitar capacidades de búsqueda por parámetros clave para agilizar la localización de un tercero específico y verificar su información sin depender de archivos planos. |

**HU\_001 Consulta general de subcontratistas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
|  | **Consulta general de subcontratistas** | **Dado que:** Los subcontratistas se gestionaban previamente de forma manual mediante rangos en archivos Excel de control de saldos sin una centralización adecuada. **Cuando:** Se requiera consultar el listado general de terceros y empresas bajo modalidad de outsourcing registrados en el sistema. **Entonces:**  Se debe mostrar una interfaz de consulta (tabla) que relacione la información clave de cada subcontratista: nombre o razón social, NIT o cédula, descripción de para qué se subcontrata, y objeto o concepto. |

**HU\_002 Filtrado y Búsqueda Avanzada de Subcontratistas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtrado y Búsqueda Avanzada de Subcontratistas** | **Dado que:** Se cuenta con una maestra centralizada de subcontratistas para la ejecución de las licitaciones y se requiere ubicar rápidamente a un tercero específico. **Cuando:** Se aplique criterios de búsqueda o filtros (por nombre/razón social o por NIT/cédula) **Entonces:** El sistema debe filtrar dinámicamente los registros y mostrar únicamente las opciones que coincidan con la búsqueda realizada. |

