

| Cambio de sucursal de la orden de trabajo |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar la OT y su sucursal actual |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Cambiar la sucursal de atención |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Cambiar la sucursal de una OT interna cuando el vehículo se traslada entre sedes, conservando el historial de traslados con fecha, sede de origen, sede de destino y motivo. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Traslado del vehículo entre sedes y actualización de la OT. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, la Orden de Trabajo (OT) carece de un registro que identifique la sucursal de atención específica en la que se encuentra el vehículo. De igual manera, el sistema no permite gestionar ni documentar traslados de vehículos entre las diferentes sedes de la serviteca. Esta restricción genera puntos ciegos en la operación multi-sede, dificultando el control de inventarios, la asignación de recursos y la visualización del estado real del servicio por parte del área administrativa |

| Situación Deseada |
| :---- |
| Se debe permitir la asignación y actualización de la sucursal de atención en la Orden de Trabajo. Cuando un vehículo requiera ser movilizado entre sedes para continuar con su servicio, la plataforma permitirá registrar este traslado, generando un historial automatizado. Esto garantizará una trazabilidad completa del recorrido del vehículo, mejorando la logística interna, el control de la operación en tiempo real y la precisión en los tiempos de entrega. |

**HU\_001 Consultar la OT y su sucursal actual**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar la OT y su sucursal actual** | **Dado que:** una OT tiene una sucursal de atención asignada **Cuando:** el coordinador consulta la OT **Entonces:** se muestra la sucursal y el satélite de atención actuales. |

**HU\_002 Cambiar la sucursal de atención**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Cambiar la sucursal de atención** | **Dado que:** el vehículo se traslada a otra sede **Cuando:** el coordinador actualiza la sucursal de atención registrando el motivo **Entonces:** la OT queda en la nueva sucursal y se registra el traslado en el historial (fecha, sede origen, sede destino y motivo). Regla de negocio: La OT interna hereda la sucursal de atención y el satélite de la recepción; la sucursal puede cambiarse si el vehículo se traslada entre sedes, conservando el historial de traslados. Regla de negocio: El ejecutor (personal interno o tercero DASA) es independiente de la sucursal o satélite donde se atiende el vehículo. |

