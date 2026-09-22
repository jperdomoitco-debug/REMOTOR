# Cambio de sucursal de la orden de trabajo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar la OT y su sucursal actual |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Cambiar la sucursal de atención |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Cambiar la sucursal de una OT interna cuando el vehículo se traslada entre sedes, conservando el historial de traslados con fecha, sede de origen, sede de destino y motivo |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Consultar la sucursal o el satélite actual, registrar cada cambio documentado con su respectivo historial de traslados, heredar los datos desde la recepción y notificar de manera automática a la sede de destino. |  |  |  |

## Situación Actual

Actualmente la Orden de Trabajo (OT) carece de un registro que identifique la sucursal de atención específica en la que se encuentra el vehículo. De igual manera, el sistema no permite gestionar ni documentar traslados de vehículos entre las diferentes sedes de la serviteca. Esta restricción genera puntos ciegos en la operación multi-sede, dificultando el control de inventarios, la asignación de recursos y la visualización del estado real del servicio por parte del área administrativa.

## Situación Deseada

Se debe permitir la asignación y actualización de la sucursal de atención en la Orden de Trabajo. Cuando un vehículo requiera ser movilizado entre sedes para continuar con su servicio, la plataforma permitirá registrar este traslado, generando un historial automatizado. Esto garantizará una trazabilidad completa del recorrido del vehículo, mejorando la logística interna, el control de la operación en tiempo real y la precisión en los tiempos de entrega.

---

## HU_001 — Consultar la OT y su sucursal actual

**Como** Coordinador administrativo,
**Quiero** consultar la sucursal y el satélite de atención actuales de una Orden de Trabajo,
**Para** conocer el estado real del servicio y controlar la operación multi-sede.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una OTi con sucursal de atención asignada (heredada de la recepción).
3. Las sucursales y satélites deben estar configurados en el sistema.

### Especificación Técnica de Comportamiento

1. **Consulta de la sucursal:** Al consultar la OTi, el sistema muestra la **sucursal** y el **satélite** de atención actuales.
2. **Búsqueda estricta:** La OTi se localiza estrictamente por **placa o sigla**; no se admite búsqueda por entidad ni por contrato.
3. **Precarga:** La sucursal y el satélite se precargan desde la recepción que dio origen a la OTi, en modo solo lectura.
4. **Historial visible:** Junto a la sucursal actual, se muestra el historial de traslados previos (fecha, sede origen, sede destino y motivo).

### Criterios UX / Usabilidad

1. **Mínimo de clics (1 clic):** un clic abre el detalle de la OTi con su sucursal y satélite actuales.
2. **Autocompletado:** sucursal y satélite precargados desde la recepción, en solo lectura.
3. **Confirmación en tiempo real:** la carga de la sucursal y del historial es asíncrona, sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Consultar la sucursal y el satélite actuales (caso feliz)**

Dado que una OTi tiene una sucursal de atención asignada
Cuando el Coordinador consulta la OTi
Entonces el sistema muestra la sucursal y el satélite de atención actuales.

**Escenario 2: Visualizar el historial de traslados (caso feliz)**

Dado que la OTi ha tenido traslados entre sedes
Cuando el Coordinador consulta el detalle de la OTi
Entonces el sistema muestra el historial de traslados con fecha, sede de origen, sede de destino y motivo.

**Escenario 3: OTi sin sucursal asignada (excepción)**

Dado que la recepción que originó la OTi no tiene sucursal de atención registrada
Cuando el Coordinador consulta la OTi
Entonces el sistema muestra el estado vacío "Sin sucursal de atención asignada".

### Matriz Delta de Cambios

**[ADDED]**
- Visualización de la sucursal y el satélite de atención actuales de la OTi.
- Historial de traslados visible junto a la sucursal actual.
- Búsqueda de la OTi por placa o sigla.

**[MODIFIED]**
- La OTi ahora identifica y muestra la sucursal de atención específica.

**[REMOVED]**
- Punto ciego de la operación multi-sede (falta de registro de sucursal).

---

## HU_002 — Cambiar la sucursal de atención

**Como** Coordinador administrativo,
**Quiero** actualizar la sucursal de atención de una OTi registrando el motivo,
**Para** documentar el traslado del vehículo entre sedes y conservar la trazabilidad completa.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una OTi con sucursal de atención asignada.
3. Deben existir sucursales y satélites configurados en el sistema.

### Especificación Técnica de Comportamiento

1. **Cambio documentado:** El Coordinador actualiza la sucursal de atención registrando obligatoriamente el motivo del traslado.
2. **Historial de traslados:** Cada cambio se registra en el historial con fecha, sede de origen, sede de destino, motivo y usuario que lo realizó.
3. **Herencia desde la recepción:** La OTi hereda la sucursal de atención y el satélite de la recepción al momento de su creación.
4. **Ejecutor independiente:** El ejecutor (personal interno o tercero DASA) es independiente de la sucursal o satélite donde se atiende el vehículo; cambiar la sucursal no modifica el ejecutor.
5. **Bloqueo por estado:** No se permite cambiar la sucursal cuando la OTi está en estado finalizado o entregado.
6. **Notificación a la sede destino:** Al registrar el traslado, el sistema notifica a la sede destino por correo, WhatsApp y alerta visual en la campanita.

### Criterios UX / Usabilidad

1. **Mínimo de clics (≤ 2 clics):** seleccionar la nueva sucursal/satélite desde una lista desplegable, registrar el motivo y confirmar.
2. **Autocompletado:** la sucursal actual se precarga y las sucursales/satélites disponibles se presentan en una lista desplegable.
3. **Confirmación en tiempo real:** el cambio y el registro en el historial se confirman sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Cambiar la sucursal registrando el motivo (caso feliz)**

Dado que el vehículo se traslada a otra sede
Cuando el Coordinador actualiza la sucursal de atención y registra el motivo
Entonces la OTi queda en la nueva sucursal y el sistema confirma el cambio.

**Escenario 2: Registrar el traslado en el historial (caso feliz)**

Dado que se realizó un cambio de sucursal
Cuando el sistema confirma el traslado
Entonces registra en el historial la fecha, sede de origen, sede de destino y motivo.

**Escenario 3: Heredar la sucursal desde la recepción (caso feliz)**

Dado que se crea una OTi a partir de una recepción
Cuando el sistema genera la OTi
Entonces la OTi hereda automáticamente la sucursal de atención y el satélite de la recepción.

**Escenario 4: Ejecutor independiente de la sucursal (caso feliz)**

Dado que una OTi tiene un ejecutor asignado (personal interno o tercero DASA)
Cuando se cambia la sucursal de atención
Entonces el sistema conserva el ejecutor sin modificar su asignación.

**Escenario 5: Notificar a la sede destino (caso feliz)**

Dado que se registró un traslado de sucursal
Cuando el sistema confirma el cambio
Entonces notifica a la sede destino por correo, WhatsApp y alerta visual en la campanita.

**Escenario 6: Bloqueo de cambio en OT finalizada (excepción)**

Dado que la OTi está en estado finalizado o entregado
Cuando el Coordinador intenta cambiar la sucursal de atención
Entonces el sistema bloquea el cambio y muestra "No se puede cambiar la sucursal de una OT finalizada".

**Escenario 7: Cambio sin motivo (excepción)**

Dado que el Coordinador intenta cambiar la sucursal sin registrar el motivo
Cuando confirma el cambio
Entonces el sistema bloquea la operación y exige registrar el motivo del traslado.

### Matriz Delta de Cambios

**[ADDED]**
- Registro obligatorio del motivo en cada traslado.
- Historial de traslados con fecha, sede de origen, sede de destino, motivo y usuario.
- Herencia de la sucursal y el satélite desde la recepción.
- Notificación a la sede destino (correo, WhatsApp y campanita).
- Bloqueo del cambio en OTi finalizada o entregada.

**[MODIFIED]**
- Cambio de sucursal ahora documentado y trazable en el sistema.

**[REMOVED]**
- Imposibilidad de gestionar y documentar traslados de vehículos entre sedes.
