

| Consultar recepciones |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar recepciones |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Aprobar recepción |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Consultar recepciones de vehículos además de automatizar la creación de órdenes de trabajo con la información del encabezado. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Consultar recepciones de los vehículos que ingresan. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente las recepciones deben ser comunicadas de manera presencial al coordinador administrativo, el asesor de servicio teniendo que desplazarse hasta el área administrativa para pasar el documento que ha sido diligenciado a mano. Esto hace que la continuidad del proceso de validación dependa de que la asesora de servicio llegue de manera oportuna a hacer la entrega de la recepción. |

| Situación Deseada |
| :---- |
| Se desea que la coordinadora administrativa pueda consultar las recepciones de los vehículos desde un formulario, en cual se podrá revisar la información y realizar las respectivas validaciones. Además de permitir la aprobación de la recepción la cual desencadenará la creación inicial de la orden de trabajo, diligenciando datos de iniciales de encabezado, como placa, entidad, kilometraje, etc. |

**HU\_001 Consultar recepciones**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar recepciones** | **Dado que:** La recepción es comunicada de manera presencial  al área administrativa mediante la entrega de un formato de recepción diligenciado. **Cuando:** Se requiere consultar las nuevas recepciones de vehículos. **Entonces:** El coordinador administrativo consultará la tabla de recepciones de vehículos. Donde podrá consultar información para proceder con las validaciones iniciales.  |

**HU\_002 Aprobar recepción**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Aprobar recepción** | **Dado que:** La creación inicial de una nueva orden de trabajo deberá ser diligenciada desde cero de manera manual en base a la información del documento de recepción; obligando a realizar trabajo manual. **Cuando:** El coordinador administrativo complete la validación de la recepción y de click en aprobar dentro de la recepción. **Entonces:** Se creará automáticamente una orden de trabajo, la cual tendrá diligenciada información del encabezado, acortando tiempos en la operación y logrando que el coordinador administrativo pueda enfocarse en los detalles de la orden de trabajo.  |

