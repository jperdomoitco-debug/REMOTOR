# Gestión de recepción

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Aprobar la recepción |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Aprobar la recepción validada |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |  |

| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Vincular una solicitud digital a la OTi permitiendo el autocompletado de la entidad, la placa y los repuestos, asegurar la trazabilidad de los estados y automatizar la notificación al almacenista. |  |  |  |

## Situación Actual

Actualmente, el proceso operativo enfrenta diversas deficiencias que van desde validaciones administrativas manuales y dispersas que retrasan la confirmación de recepciones, hasta la falta de visibilidad y directrices claras **Cuando** faltan documentos externos indispensables como la OTe. Asimismo, la comunicación informal con el jefe de taller mediante llamadas o chats genera retrasos innecesarios, problemática que se ve agravada por la ausencia de bloqueos de inmutabilidad en los registros aprobados, lo cual vulnera la trazabilidad exacta y expone los datos a modificaciones indebidas.

## Situación Deseada

Implementar una aprobación ágil y centralizada que permite al coordinador administrativo validar los registros en máximo dos clics de forma inmediata, complementada con un control inteligente de documentos que gestiona escenarios con o sin orden externa y bloquea la aprobación mediante un indicador explícito si falta el archivo requerido. Asimismo, automatiza las notificaciones para alertar al jefe de taller vía PUSH o WhatsApp tan pronto se habilita un vehículo para diagnóstico, y garantiza una trazabilidad total y seguridad mediante registros inmutables de solo lectura respaldados por un log automático con fecha, hora y usuario exacto.

## HU_001 — Aprobar la recepción

**Como** Coordinador administrativo,
**Quiero** aprobar la recepción validada,
**Para** confirmar que la recepción cumple con la información requerida y habilitar la continuidad del proceso.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una recepción con su información validada.
**3.** El vehículo de la recepción debe estar registrado y validado en el sistema (si no estaba registrado, ya fue completado y guardado por coordinación).

### Especificación Técnica de Comportamiento

**1.** **Aprobación:** Al pulsar "Aprobar", el sistema confirma la aprobación de la recepción y cambia su estado a aprobado.
**2.** **Caso A (con OTe):** Si la recepción tiene orden externa cargada, el coordinador revisa el PDF/foto, valida la orden y aprueba la recepción; el proceso continúa con la información de la orden externa disponible.
**3.** **Caso B (sin OTe):** Si la recepción no tiene orden externa, el coordinador aprueba la recepción y el proceso continúa sin orden externa cargada.
**4.** **Notificación de habilitación:** Al aprobar, el sistema dispara una notificación (PUSH/WhatsApp) al jefe de taller: *"Vehículo [Placa/Sigla] habilitado para diagnóstico"*.
**5.** **Carga de orden pendiente:** Si la recepción indica "con orden externa" pero no trae documento cargado, el sistema muestra el indicador "cargar orden" y permite cargar el documento antes de aprobar.
**6.** **Inmutabilidad:** Una recepción aprobada queda inmutable y no puede editarse ni volver a aprobarse.
**7.** **Trazabilidad:** Se registra log con fecha, hora y usuario que aprobó la recepción.

### Criterios UX / Usabilidad

**1.** **Mínimo de clics (≤ 2 clics):** validar y aprobar desde el detalle de la recepción con un solo clic.
**2.** **Confirmaciones en tiempo real:** al aprobar, el sistema confirma la aprobación de la recepción y el cambio de estado sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Aprobar la recepción (caso feliz)**

**Dado que** el Coordinador validó la información de la recepción
**Cuando** pulsa "Aprobar" en el detalle de la recepción
**Entonces** el sistema aprueba la recepción.

**Escenario 2: Aprobar con orden externa (caso feliz)**

**Dado que** la recepción tiene la orden externa cargada
**Cuando** el Coordinador revisa el PDF/foto y aprueba
**Entonces** la recepción queda aprobada y la información de la orden externa queda disponible para la continuidad del proceso.

**Escenario 3: Aprobar sin orden externa (caso feliz)**

**Dado que** la recepción no tiene orden externa
**Cuando** el Coordinador aprueba
**Entonces** la recepción queda aprobada y el proceso continúa sin orden externa cargada.

**Escenario 4: Notificar la habilitación al jefe de taller (caso feliz)**

**Dado que** el Coordinador aprobó la recepción
**Cuando** la recepción cambia a estado aprobado
**Entonces** el sistema envía notificación PUSH/WhatsApp al jefe de taller indicando que el vehículo quedó habilitado para diagnóstico.

**Escenario 5: Cargar la orden externa pendiente (excepción)**

**Dado que** la recepción indica "con orden externa" pero no trae el documento cargado
**Cuando** el Coordinador consulta la recepción
**Entonces** el sistema muestra el indicador "cargar orden" y permite cargar el documento antes de aprobar.

**Escenario 6: Bloqueo de aprobación sin validación (excepción)**

**Dado que** la recepción tiene información incompleta o inconsistente
**Cuando** el Coordinador intenta aprobarla
**Entonces** el sistema bloquea la aprobación y exige completar o validar los datos antes de continuar.

**Escenario 7: Inmutabilidad de la recepción aprobada (excepción)**

**Dado que** la recepción ya fue aprobada
**Cuando** se intenta editarla o aprobarla nuevamente
**Entonces** el sistema bloquea la edición y no permite una segunda aprobación.

**Escenario 8: Trazabilidad de la aprobación (caso feliz)**

**Dado que** el Coordinador aprobó la recepción
**Cuando** consulta el historial de la recepción
**Entonces** el sistema registra la fecha, hora y usuario que aprobó la recepción.

### Matriz Delta de Cambios

**[ADDED]**

- Aprobación de la recepción validada desde su detalle.
- Notificación PUSH/WhatsApp al jefe de taller al habilitar el diagnóstico.
- Indicador "cargar orden" para la orden externa pendiente.
- Inmutabilidad de la recepción una vez aprobada.
- Trazabilidad de la aprobación mediante fecha, hora y usuario.

**[MODIFIED]**

- Aprobación: la recepción pasa a estado aprobado únicamente después de que el Coordinador valida la información requerida.
- Flujo de recepción clarificado para los casos con y sin orden externa.

**[REMOVED]**

- Creación de la Orden de Trabajo interna dentro de esta HU.
- Generación automática de la Orden de Trabajo interna como resultado de la aprobación.
- Diligenciamiento del encabezado de la Orden de Trabajo dentro de esta HU.
- Consecutivo de la Orden de Trabajo dentro de esta HU.
- Estados de la Orden de Trabajo dentro de esta HU.
