

| Configuración de parámetros de prefactura |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Configuración de  reglas de prefactura por entidad |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Vinculación y carga de plantillas excel personalizadas |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Configuración de parámetros de prefactura |  |  |  |

| Situación Actual |
| :---- |
| Actualmente no existe un estándar unificado para la generación de prefacturas, ya que cada entidad contratante exige un formato y una estructura de datos específica (algunas solicitan información consolidada por orden y dependencia, mientras que otras exigen un listado detallado de ítems con cantidades, valores con/sin IVA y totales) La generación de estas prefacturas se resuelve mediante métodos dispares: Con algunos clientes se utilizan scripts personalizados en Google Apps Script para consolidar órdenes y generar hojas dependientes por entidad. Con otros clientes el proceso es completamente manual mediante el uso de matrices de precios en hojas de cálculo. No hay un motor centralizado que configure qué datos deben alimentarse hacia los reportes de facturación según los requerimientos particulares de cada entidad. |

| Situación Deseada |
| :---- |
| Implementar una estructura centralizada que permita definir y saber exactamente qué data pasarle al reporte de la factura de acuerdo con los requerimientos específicos solicitados por cada entidad donde permita la vinculación de un archivo de plantilla en Excel que reciba variables dinámicas, las cuales puedan ser reemplazadas automáticamente con la información configurada en el sistema para adaptarse al formato exigido por cada entidad. Tambien soportar las distintas modalidades de presentación exigidas (consolidados por orden y dependencia, o listados detallados de ítems con desglose de cantidades, valores con/sin IVA y totales). |

**HU\_001 Configuración de  reglas de prefactura por entidad**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Configuración de  reglas de prefactura por entidad** | **Dado que:** Cada entidad contratante exige una estructura de datos distinta para su facturación. **Cuando:** la gerencia operativa configura los parámetros de facturación para una entidad específica. **Entonces:** Se debe permitir seleccionar y asociar las reglas de negocio correspondientes (ej. tipo de consolidación por orden/dependencia o desglose de ítems, cantidades, IVA y totales) para que la data extraída coincida con lo solicitado. |

**HU\_002  Vinculación y carga de plantillas excel personalizadas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Vinculación y carga de plantillas excel personalizadas** | **Dado que:** Las entidades manejan formatos visuales y plantillas de Excel propias que reemplazan el uso de scripts aislados o matrices manuales. **Cuando:** Se requiere asociar el formato de un cliente en el sistema. **Entonces:** El sistema debe permitir adjuntar y almacenar un archivo de plantilla en formato Excel (.xlsx) vinculado directamente a la configuración de la entidad.  |

