

| Gestión de oferta económica |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Actualización de maestra de procedimientos y precios |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Registro de vehículos nuevos y asociación a contrato |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Vinculación de vehículos existentes a múltiples contratos |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Quiero importar las ofertas económicas mediante una plantilla de Excel con un formato común, para centralizar la maestra de procedimientos, registrar los vehículos y asociar los precios específicos (repuestos y mano de obra) a cada contrato en el sistema. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Gestión de oferta económica |  |  |  |

| Situación Actual |
| :---- |
| Para la operación y órdenes de trabajo se maneja un archivo de Excel ("control de saldos") donde está la oferta económica. Cada contrato o entidad puede entregar su oferta en un formato distinto, lo que obliga a depender de ese archivo externo y de procesos manuales para identificar los vehículos, los procedimientos y los precios al momento de operar. |

| Situación Deseada |
| :---- |
| Tener un módulo en el sistema que reciba un archivo Excel estandarizado (un formato común para todas las ofertas, sin importar la entidad de origen). Al subir este archivo, el sistema debe poblar automáticamente la maestra de procedimientos, registrar los vehículos (con placa, sigla, marca, cilindraje) y asociar tanto los vehículos como los precios correspondientes a su respectivo contrato, soportando que una misma placa pertenezca a múltiples contratos simultáneamente. |

**HU\_001 Actualización de maestra de procedimientos y precios**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Actualización de maestra de procedimientos y precios** | **Dado que el usuario**: Se tiene el archivo Excel estandarizado con la información de la oferta económica de un contrato **Cuando:** Sube el archivo al módulo de carga masiva **Entonces:** El sistema procesa el formato común, inserta los ítems que no existan en la maestra de procedimientos y asocia los valores monetarios de repuestos y mano de obra a ese contrato específico. |

**HU\_002 Registro de vehículos nuevos y asociación a contrato**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Registro de vehículos nuevos y asociación a contrato** | **Dado que:** El sistema está procesando las filas del archivo Excel durante la carga **Cuando:** Lee las propiedades de un vehículo (placa, marca, cc, sigla) **Entonces:** Valida si la placa ya existe en la base de datos; si no existe lo crea, y asocia ese vehículo al contrato actual para habilitarle dicha oferta económica.  |

**HU\_003 Vinculación de vehículos existentes a múltiples contratos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Vinculación de vehículos existentes a múltiples contratos** | **Dado que:** Una placa ya está registrada en el sistema y asociada a un contrato previo **Cuando:** se procesa un nuevo archivo estandarizado de un contrato diferente que incluye esa misma placa **Entonces:** el sistema no duplica la creación del vehículo, sino que asocia esa placa existente al nuevo contrato, permitiendo que el vehículo pueda operar bajo las condiciones de ambas entidades. |

