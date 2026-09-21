

| Crear proveedor |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Crear proveedor |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Control de calidad de la información |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Almacenista |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Quiero contar con un módulo centralizado de gestión de proveedores que permita el registro, validación y consulta de sus catálogos, eliminando la dispersión de información y los errores manuales actuales, para agilizar los procesos de compra y asegurar visibilidad y precisión en tiempo real. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Compras |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Crear nuevos proveedores. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, no existe un módulo centralizado para la gestión de proveedores, lo que provoca que el registro sea manual, disperso y propenso a errores. No hay una forma directa y eficiente de validar qué productos o servicios provee cada proveedor, lo que genera retrasos operativos, falta de visibilidad en el catálogo y retrabajos al buscar información actualizada para realizar compras. |

| Situación Deseada |
| :---- |
| Implementar un módulo unificado de gestión de proveedores dentro del sistema que permita el registro, validación y consulta centralizada. El objetivo es asegurar que todos los proveedores estén correctamente clasificados y tengan su catálogo de productos asociado, garantizando información precisa, estructurada y disponible en tiempo real para optimizar el flujo de trabajo del almacenista y reducir errores en la cadena de suministro. |

**HU\_001 Título de historia de usuario**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Crear proveedor** | **Dado que:** necesito registrar un nuevo proveedor; **Cuando:** Se ingrese la información fiscal, de contacto y los ítems asociados; **Entonces:** el sistema valida la estructura de los datos y crea el registro confirmando su disponibilidad para futuras cotizaciones. **3\. Consulta ágil de catálogo:** **Dado que:** Se requiere verificar qué suministros ofrece un proveedor; **Cuando:** Busco un proveedor específico en el sistema; **Entonces:** el sistema me muestra su perfil completo, incluyendo la lista detallada de los artículos que suministra, facilitando una selección rápida y precisa. |

**HU\_002 Control de calidad de la información**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Control de calidad de la información** | **Dado que:** el sistema debe asegurar datos de alta calidad; **Cuando:** intento guardar un proveedor sin completar los campos obligatorios o con información incompleta; **Entonces:** el sistema bloquea el guardado y me notifica específicamente qué datos faltan por diligenciar. |

