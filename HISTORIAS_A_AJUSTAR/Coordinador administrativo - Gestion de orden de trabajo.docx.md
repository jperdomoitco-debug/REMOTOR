

| Gestión de orden de trabajo |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Crear orden de trabajo cuando se cree la recepción |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Enviar solicitud de aprobación al supervisor |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Actualizar información de la orden de trabajo |  |  |  |  |  |  |  |  |  |
| HU\_004 |  | Consultar ordenes de trabajo |  |  |  |  |  |  |  |  |  |
| HU\_005 |  | Consultar historial de aprobaciones |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Crear la orden de trabajo al momento de que se registre la recepción de un vehículo, además del envío del flujo de aprobación al supervisor de la entidad. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Crear la orden de trabajo al momento de que se registre la recepción de un vehículo |  |  |  |

| Situación Actual |
| :---- |
| Actualmente la creación de la orden de trabajo debe ser creada inicialmente en base a la información que se recibe desde la zona de recepción. Dicha información puede ser suministrada vía chat, enviando un pantallazo del formato o la entrega presencial del documento físico. Dicho proceso requiere que el coordinador administrativo traslade la información de manera manual desde documento de recepción al formato de orden de trabajo en excel. Dicho proceso requiere una cantidad de tiempo importante además de ser susceptible a errores de digitación. |

| Situación Deseada |
| :---- |
| Se desea que la creación de las órdenes de trabajo se ejecuten de manera automática al momento de que se registre una nueva recepción de vehículo. Esta orden de trabajo heredará la información que llega desde el documento de recepción. Quedando como trabajo pendiente la especificación de los detalles de la orden de trabajo dependiendo de la entidad a la que se recibe el vehículo.  |

**HU\_001 Crear orden de trabajo cuando se cree la recepción**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Crear orden de trabajo cuando se cree la recepción** | **Dado que:** La orden de trabajo debe ser creada de manera manual en base a la información que llega desde la recepción del vehículo. **Cuando:** Se genere un nuevo documento de recepción. **Entonces:** Se debe crear de manera automática una orden de trabajo en base a la información de la recepción donde extraiga datos como, placa, entidad, líneas de los trabajos a realizar, etc. Logrando una reducción drástica al momento de que el coordinador administrativo comience a detallar y especificar mejor la orden de trabajo. Importante: Aunque se planea crear de manera automática se debe dar la opción de crear órdenes de trabajo de manera manual  Regla de negocio: Para crear una orden de trabajo debe si o si relacionarse con un documento de recepción. |

**HU\_002 Enviar solicitud de aprobación al supervisor**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Enviar solicitud de aprobación al supervisor** | **Dado que:** Actualmente la aprobación de las órdenes de trabajo por parte del supervisor de la entidad se realizan vía Whatsapp, es decir, se envía información pertinente sobre el trabajo a realizar al supervisor de la entidad y esté realiza una confirmación, negación o solicitud de ajuste directamente en el chat de Whatsapp. Perdiendo la trazabilidad de las aprobaciones ya sean totales o parciales, rechazo y el motivo del mismo. **Cuando:** Cuando se prepare de manera total la orden de trabajo y se desee comunicar al supervisor de la entidad con intención de recibir aprobación. **Entonces:** Desde la orden de trabajo se enviará la solicitud de aprobación al correo que es indicado por la entidad para dicho fin. La coordinadora administrativa será la encargada de adjuntar la evidencia fotográfica del correo y su respuesta a la orden de trabajo, ya sea aprobada, rechazada o aprobada parcialmente.  Regla de negocio: Una orden de trabajo puede ser enviada al flujo de aprobación varias veces, principalmente cuando se añaden nuevos ítems que representan nuevos hallazgos durante el diagnóstico del vehículo. |

**HU\_003 Actualizar información de la orden de trabajo**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Actualizar información de la orden de trabajo** | **Dado que:** Actualmente los nuevos hallazgos deben ser transcritos y traducidos desde el documento de diagnóstico o comunicados de manera verbal al coordinador administrativo. Haciendo que sea un proceso poco óptimo que obliga a extender tiempos y quitar enfoque en sus labores operativas al jefe de taller. **Cuando:** Cuando se crea un nuevo documento de diagnóstico. **Entonces** se debe hacer el proceso de homologación de los términos que maneja el taller con los que maneja la entidad. Posteriormente se debe actualizar la orden de trabajo agregando estos nuevos elementos. Importante: La orden siempre va a permitir ajustarse desde el área administrativa antes de enviar al flujo de aprobación.  |

**HU\_004 Consultar ordenes de trabajo**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar ordenes de trabajo** | **Dado que:** se requiere trazabilidad**Cuando:** se consulta el historial de la OT**Entonces:** se debe mostrar un listado con todas las órdenes de trabajo, las que estan guardas y no ha sido enviada a aprobación y las que ya han cumplido el ciclo de ejecucion.  |

**HU\_005 Consultar historial de aprobaciones**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar historial de aprobaciones** | **Dado que:** se requiere trazabilidad**Cuando:** se consulta el historial de la OT**Entonces:** se debe mostrar cada envío con su fecha, resultado, ítems OK/NO y soportes adjuntos. |

