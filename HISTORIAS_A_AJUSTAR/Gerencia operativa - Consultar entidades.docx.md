

| Consultar entidades |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Visualización de listado general de entidades |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Búsqueda avanzada de entidades |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar entidades |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, para realizar la consulta de las entidades, se requiere navegar en Google Drive. Cada entidad está representada en una carpeta, por lo que no existe una manera específica de ver un listado general como fuente de la verdad, más allá de la segmentación existente (ej. Taller González y Revolución Motor). |

| Situación Deseada |
| :---- |
| Contar con una vista centralizada o un módulo de consulta que permita visualizar todas las entidades registradas en un listado general. Esta solución debe actuar como una fuente de la verdad unificada, eliminando la necesidad de navegar carpeta por carpeta en Google Drive y permitiendo una gestión más eficiente de la información de todas las entidades, |

**HU\_ 001 Visualización de listado general de entidades**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Visualización de listado general de entidades** | **Dado que:**  La Gerencia Operativa accede al sistema. **Cuando:**  Selecciona la opción de consultar entidades. **Entonces:**  El sistema debe mostrar un listado consolidado de todas las entidades registradas. |
| **2** | **Filtros y orden del listado** | **Dado que:**  El listado de entidades está visible. **Cuando:**  Se aplican filtros por sector, estado, o se ordena por nombre. **Entonces:**  El sistema filtra y ordena los resultados en tiempo real. |

**HU\_002 Búsqueda avanzada de entidades**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Búsqueda avanzada de entidades** | **Dado que:** el usuario se encuentra en el listado general de entidades. **Cuando:** ingresa el nombre de una entidad o un filtro específico en la barra de búsqueda. **Entonces:** el sistema debe filtrar los resultados en tiempo real mostrando solo las entidades que coincidan con los criterios de búsqueda. |

