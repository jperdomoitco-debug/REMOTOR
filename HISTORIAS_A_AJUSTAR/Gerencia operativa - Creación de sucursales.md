

| Creación de sucursales  |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación de Sucursal |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Creación de sucursal satélite |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Crear sucursales principales por ciudad y sucursales satélites de apoyo, con su clasificación y jerarquía, para soportar la expansión de la operación a nivel nacional. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creación de sucursales |  |  |  |

| Situación Actual |
| :---- |
| Actualmente no existe en el sistema una segmentación ni una estructura formal para definir sucursales o puntos de operación. La gestión operativa se maneja sin la capacidad de segregar geográficamente los recursos, lo que limita la cobertura y el control sobre los diferentes puntos de trabajo. |

| Situación Deseada |
| :---- |
| Se planea expandir y escalar la operación a nivel nacional mediante la creación de sucursales principales por ciudad y unidades satélites más pequeñas para apoyar la operación técnica. Clasificación Estructural: Sucursales: Sedes principales que operan a nivel de ciudad o región. Sucursales Satélites: Unidades de apoyo que dependen de una sucursal específica dentro de la misma ciudad (pueden ser talleres pequeños, servitecas propias o talleres tercerizados especializados en áreas técnicas específicas). Importante: Estas sucursales deben manejar el mismo estándar en cuanto al flujo para garantizar una operación óptima y efectiva. |

**HU\_001 Creación de Sucursal**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación de Sucursal** | **Dado que:** Se planea realizar expansiones y escalar la operación a nivel nacional mediante sucursales por ciudad.. **Cuando:** Se requiere dar de alta una nueva sede o sucursal principal en el sistema. **Entonces:** El sistema debe permitir crear un registro de sucursal asociando su respectiva ubicación (ciudad) para soportar la operación principal La información a tener en cuenta es la siguiente: Nombre de la sucursal: Identificador o nombre comercial de la sede (ej. Sucursal Cali Norte). Ciudad / Ubicación: Ciudad principal donde operará la sede para permitir el escalamiento a nivel nacional. Dirección: Ubicación física de la sucursal. Responsable / Administrador: Persona encargada de la operación de la sede |

**HU\_002 Creación de sucursal satélite**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Creación de Sucursal Satélite** | **Dado que:** Se requieren unidades de apoyo más pequeñas que dependen de una sucursal específica dentro de la misma ciudad (como talleres pequeños, servitecas propias o talleres tercerizados especializados). **Cuando:** Se requiere registrar una nueva unidad satélite para descentralizar y apoyar la operación. **Entonces:** El sistema debe permitir crear una sucursal satélite vinculándola de forma dependiente a su sucursal principal correspondiente. La información a tener en cuenta es la siguiente: Nombre del satélite: Identificador de la unidad de apoyo (ej. Taller autorizado Sur). Sucursal principal asociada: Sucursal dependiente que la vincula directamente con la sucursal principal de la ciudad de la cual depende. tipo de unidad satélite: Clasificación del tipo de apoyo (taller pequeño, serviteca propia o taller tercerizado especializado en áreas técnicas específicas). Dirección o Ubicación: Dónde se encuentra ubicada físicamente la unidad satélite. Responsable / Administrador: Persona encargada de la operación de la sede. |

