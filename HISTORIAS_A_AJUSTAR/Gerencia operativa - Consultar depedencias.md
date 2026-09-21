

| Consultar dependencias |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consulta y listado de la maestra de dependencias |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtrado y búsqueda avanzada de dependencias |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar dependencias |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, las dependencias se manejan de manera aislada dentro del archivo Excel de "control de saldos", lo que impide tener una centralización, visibilidad y trazabilidad adecuada sobre las subdivisiones de las entidades y sus presupuestos contractuales. Al no existir una tabla maestra dedicada a nivel de sistema, la consulta de qué dependencias están asociadas a cada entidad se realiza de forma manual, dificultando el seguimiento operativo y presupuestal. |

| Situación Deseada |
| :---- |
| Implementar una interfaz de consulta y listado para la Gerencia Operativa que permita visualizar de forma clara todas las dependencias registradas. Facilitar la búsqueda y el filtrado de las dependencias asociadas a cada entidad contratante para asegurar su vinculación con los presupuestos contractuales. |

**HU\_001 Consulta y listado de la maestra de dependencias**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consulta y listado de la maestra de dependencias** | **Dado que:**  Las dependencias se gestionaban previamente en un archivo Excel de control de saldos sin una centralización ni trazabilidad adecuada para definir subdivisiones de entidades y configurar presupuestos. **Cuando:**  La gerencia operativa accede  a consultar las dependencias. **Entonces:**  El sistema debe permitir listar y filtrar las dependencias registradas, mostrando claramente los campos clave de su configuración: nombre de la dependencia, entidad asociada y descripción. |

**HU\_002 Filtrado y búsqueda avanzada de dependencias**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtrado y Búsqueda Avanzada de Dependencias** | **Dado que:** Las dependencias se gestionan en un Excel de control de saldos sin trazabilidad, y se requiere ubicar rápidamente subdivisiones de entidades para configurar presupuestos contractuales. **Cuando:** La gerencia operativa aplica filtros de búsqueda (por nombre de dependencia o por entidad asociada). **Entonces:**  El sistema debe filtrar dinámicamente el listado y mostrar únicamente los registros que coincidan con los criterios seleccionados, mostrando su nombre, entidad asociada y descripción. |

