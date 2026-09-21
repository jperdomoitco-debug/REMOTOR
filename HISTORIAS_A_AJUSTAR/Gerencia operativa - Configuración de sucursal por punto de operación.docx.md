

| Configuración de sucursal por punto de operación |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Configurar la sucursal de atención por punto de operación |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Recepción automática de la sucursal |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | Asignar sucursal satélite por desbordamiento |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Preconfigurar la sucursal (o sucursal satélite) de atención por punto de operación, de modo que la recepción y la OT interna tomen automáticamente la sede configurada (campo oculto/automático) sin intervención del asesor; la coordinación administrativa asigna la sucursal satélite por desbordamiento cuando la sucursal principal está llena. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Configuración de la sucursal de atención por punto de operación. |  |  |  |

| Situación Actual |
| :---- |
| Hoy la operación se realiza en un único punto de operación (Taller González) sin diferenciar la sucursal de atención; al expandir a sucursales por ciudad y sucursales satélites, la recepción no debe cargar manualmente la sede. |

| Situación Deseada |
| :---- |
| Cada punto de operación (sucursal o sucursal satélite) tiene configurada su sede de atención; la recepción toma esos valores automáticamente y la coordinación administrativa asigna la sucursal satélite por desbordamiento cuando la sucursal principal está llena. |

**HU\_001 Configurar la sucursal de atención por punto de operación**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Configurar la sucursal de atención por punto de operación** | **Dado que:** se opera en varios puntos **Cuando:** la gerencia operativa configura el punto de operación (sucursal o sucursal satélite) con su sede de atención **Entonces:** el punto de operación queda vinculado a esa sucursal para todas las recepciones. |

**HU\_002 Recepción automática de la sucursal**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **2** | **Recepción automática de la sucursal** | **Dado que:** un vehículo llega a un punto de operación configurado **Cuando:** se crea la recepción **Entonces:** el sistema asigna automáticamente la sucursal (o satélite) de atención mediante un campo oculto/automático, sin intervención del asesor. |

**HU\_003 Asignar sucursal satélite por desbordamiento**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **3** | **Asignar sucursal satélite por desbordamiento** | **Dado que:** la sucursal principal está llena**Cuando:** la coordinación administrativa requiere derivar la atención a una sucursal satélite**Entonces:** asigna la sucursal satélite de la misma ciudad en la OT, quedando registrada la asignación en el proceso. |

