

| Gestión de cortes y prefactura |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación y selección de órdenes para cortes de facturación |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Gestión y ajuste de órdenes de trabajo  en el corte de facturación |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Descarga del archivo excel de prefactura según configuración |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Facturador |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Gestionar cortes de facturación de manera centralizada mediante la selección, ajuste y descarga automatizada de órdenes de trabajo en formato Excel, para estandarizar los cobros y evitar reprocesos. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Facturación |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Gestión de cortes y prefactura |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, la facturación se realiza mediante la ejecución de scripts independientes o de forma manual utilizando matrices en Excel, lo que genera reprocesos y falta de estandarización en el control de los cobros. No hay un modo centralizado que gestiona ciclos o cortes de facturación estructurados, dificultando el seguimiento de qué órdenes de trabajo ya han sido facturadas o cuáles están pendientes de cobro. |

| Situación Deseada |
| :---- |
| Implementar un flujo donde el facturador pueda crear cortes de facturación seleccionando únicamente las órdenes de trabajo (OT) que no han sido incluidas en cortes anteriores. Proveer herramientas de visualización y filtrado por fecha y códigos de órdenes para asegurar la precisión de la información antes de consolidar el corte. Permitir ajustar el contenido del corte (anexar o remover OT según sea necesario) y descargar un archivo Excel estructurado automáticamente de acuerdo con la configuración de prefactura previamente establecida para cada entidad. |

**HU\_001 Creación y selección de órdenes para cortes de facturación**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación y selección de órdenes para cortes de facturación** | **Dado que:** actualmente la facturación se realiza mediante scripts o matrices manuales y se requiere estructurar los cobros por ciclos o cortes. **Cuando:**  Se accede a la opción de crear un nuevo corte de facturación. **Entonces:**  Se debe mostrar un listado de previsualización con las órdenes de trabajo disponibles que no han sido incluidas en cortes de facturación anteriores, permitiendo aplicar filtros por fecha y código de OT para seleccionarlas e integrarlas al corte. |

**HU\_002 Gestión y ajuste de órdenes de trabajo  en el corte de facturación**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Gestión y ajuste de órdenes de trabajo  en el corte de facturación** | **Dado que:**  Se ha creado un corte de facturación preliminar con un conjunto seleccionado de órdenes de trabajo. **Cuando:**  Se detecte alguna inconsistencia o requiera modificar el contenido del corte. **Entonces:**  Se debe permitir anexar nuevas órdenes de trabajo pendientes o remover las que estén erróneas antes de la consolidación final. |

**HU\_003 Descarga del archivo excel de prefactura según configuración**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Descarga del archivo excel de prefactura según configuración** | **Dado que:** Se cuenta con un corte de facturación estructurado y con las reglas o parámetros de prefactura configurados previamente para la entidad. **Cuando:**  Se seleccione la opción de descargar el corte de prefactura. **Entonces:**  Se debe generar y descargar un archivo en formato Excel (.xlsx) que contenga la información organizada de acuerdo con la configuración y plantilla establecida para dicha entidad. |

