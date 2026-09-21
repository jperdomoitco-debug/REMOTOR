

| Liquidación de pago a subcontratistas |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Parametrizar el % de pago a subcontratistas |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Calcular la liquidación |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Registrar el soporte del pago |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Liquidar el pago a los subcontratistas que ejecutan la reparación, aplicando un porcentaje parametrizable por contrato sobre lo facturado y descontando los repuestos tomados del almacén interno; el pago se ejecuta por fuera del sistema y solo se registra su soporte (recibo). |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Facturación  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Liquidación de pago a subcontratistas. |  |  |  |

| Situación Actual |
| :---- |
| El pago al subcontratista se calcula de forma manual: 30% de lo cobrado a la entidad menos el valor de los repuestos del almacén interno. No hay registro sistematizado ni histórico de liquidaciones. |

| Situación Deseada |
| :---- |
| El sistema calcula la liquidación automáticamente con el % parametrizado por contrato y descuenta los repuestos del almacén interno; el pago se ejecuta en la plataforma bancaria por fuera del sistema y se registra su soporte (recibo), quedando la notificación al subcontratista como un proceso manual. |

**HU\_001 Parametrizar el % de pago a subcontratistas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Parametrizar el % de pago a subcontratistas** | **Dado que:** cada contrato/subcontratista puede tener un porcentaje de pago distinto **Cuando:** el coordinador configura el contrato **Entonces:** el sistema permite definir el % de pago a subcontratistas (por defecto 30%) y su vigencia. |

**HU\_002 Calcular la liquidación**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Calcular la liquidación** | **Dado que:** una OT fue ejecutada por un subcontratista **Cuando:** el coordinador inicia la liquidación **Entonces:** el sistema calcula el % de lo facturado, descuenta los repuestos del almacén interno y muestra el valor neto a pagar. |

**HU\_003 Registrar el soporte del pago**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **3** | **Registrar el soporte del pago** | **Dado que:** la liquidación está calculada y el pago fue ejecutado en la plataforma bancaria por fuera del sistema **Cuando:** el coordinador adjunta el recibo o constancia del pago **Entonces:** el sistema registra el soporte del pago para su trazabilidad; la notificación al subcontratista se realiza de forma manual por WhatsApp u otro medio. |

