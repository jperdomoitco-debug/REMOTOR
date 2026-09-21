

| Aprobar órdenes de compra y registrar el soporte del pago |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar OC pendientes de aprobación |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Aprobar o rechazar la OC |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Registrar el soporte del pago |  |  |  |  |  |  |  |  |  |
| HU\_004 |  | Consultar historial de aprobaciones y soportes de pago |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Jefe de compras |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Consultar, aprobar o rechazar las órdenes de compra (OC) generadas por el almacenista, garantizando trazabilidad y el cumplimiento del control de saldos; y registrar el soporte del pago (recibo o constancia) cuando este se ejecuta por fuera del sistema. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Compras |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Aprobación de órdenes de compra y registro del soporte del pago. |  |  |  |

| Situación Actual |
| :---- |
| La aprobación de las OC se gestiona de forma verbal o por canales informales, sin dejar trazabilidad del aprobador, la fecha ni el motivo. El pago se ejecuta en la plataforma bancaria por fuera del sistema y no queda registrado el soporte del pago. |

| Situación Deseada |
| :---- |
| Flujo digital de ciclo cerrado: el almacenista envía la OC a aprobación, el jefe de compras la aprueba o rechaza con motivo; el pago se ejecuta en la plataforma bancaria por fuera del sistema y, una vez realizado, se adjunta el recibo como soporte del pago. Queda historial auditable de cada aprobación y de los soportes de pago. |

**HU\_001 Consultar OC pendientes de aprobación**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar OC pendientes de aprobación** | **Dado que:** el almacenista ha enviado una OC a aprobación **Cuando:** el jefe de compras consulte las OC pendientes **Entonces:** se debe mostrar un listado filtrable por estado, contrato y proveedor, con el detalle de la OT, los ítems y valores. |

**HU\_002 Aprobar o rechazar la OC**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Aprobar o rechazar la OC** | **Dado que:** la OC cumple con las condiciones del cuadro de control y el margen **Cuando:** el jefe de compras registre su decisión **Entonces:** la OC pasa a estado aprobada o rechazada con motivo, notificando al almacenista. |

**HU\_003 Registrar el soporte del pago**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **3** | **Registrar el soporte del pago** | **Dado que:** la OC está aprobada y el pago fue ejecutado en la plataforma bancaria por fuera del sistema **Cuando:** el responsable adjunta el recibo o constancia del pago a la OC **Entonces:** el sistema registra el soporte del pago asociado a la OC para su trazabilidad, sin ejecutar ni aprobar el pago desde la aplicación. |

**HU\_004 Consultar historial de aprobaciones y soportes de pago**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **4** | **Consultar historial de aprobaciones y soportes de pago** | **Dado que:** se requiere auditar las aprobaciones y los pagos **Cuando:** se consulte el historial de una OC u OT **Entonces:** se debe mostrar quién aprobó, cuándo, el estado y los soportes de pago asociados. |

