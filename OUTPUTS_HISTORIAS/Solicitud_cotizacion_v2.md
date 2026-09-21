# Solicitud de cotización

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Solicitar la cotización de repuestos |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Estandarizar la solicitud de cotizaciones al almacenista mediante un formulario digital vinculado a la orden de trabajo |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Solicitar cotización. |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Transformación a versión 2.0: solicitud digital vinculada a la OTi con autocompletado de entidad, placa y repuestos, trazabilidad de estados y notificación al almacenista |  |  |  |

## Situación Actual

La solicitud de cotizaciones se realiza actualmente de forma verbal o mediante notas informales entre el área administrativa y la encargada de inventario. Este proceso carece de trazabilidad, estandarización y registro centralizado. Como resultado, se presentan interrupciones operativas, falta de visibilidad sobre el estado de las solicitudes y tiempos de respuesta ineficientes por la dependencia de la interacción manual y presencial.

## Situación Deseada

Implementar un proceso estandarizado y digital para la solicitud y gestión de cotizaciones de repuestos, reemplazando los canales informales por una plataforma de registro centralizado que garantice la trazabilidad de cada requerimiento desde su origen hasta la respuesta final. El nuevo flujo asegurará que todas las solicitudes incluyan la información necesaria desde el primer contacto (entidad, placa y repuestos a cotizar), evitando reprocesos y consultas adicionales entre áreas, y proporcionará visibilidad en tiempo real del estado de cada gestión.

---

## HU_001 — Solicitar la cotización de repuestos

**Como** Coordinador administrativo,
**Quiero** solicitar cotizaciones de repuestos mediante un formulario digital vinculado a la Orden de Trabajo interna (OTi),
**Para** centralizar la información, eliminar reprocesos y garantizar un seguimiento efectivo de cada requerimiento.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una OTi vinculada con el diagnóstico y los repuestos a cotizar.
3. El trabajo debe ser realizado por **personal técnico interno** (regla de negocio: no aplica cuando el trabajo lo ejecuta un tercero).

### Especificación Técnica de Comportamiento

1. **Formulario vinculado a la OTi:** La solicitud de cotización se genera desde un formulario asociado a la orden de trabajo.
2. **Autocompletado:** Al abrir el formulario, se precargan la entidad, la placa y los repuestos a cotizar desde la OTi y el diagnóstico, aplicando la homologación de términos entre taller y entidad.
3. **Envío al almacenista:** La solicitud se envía con la información completa (entidad, placa y repuestos a cotizar) para que el almacenista realice una cotización efectiva.
4. **Trazabilidad de estados:** Cada solicitud registra su estado (pendiente, en proceso, respondida) y queda enlazada a la OTi.
5. **Notificación multicanal:** Al enviar la solicitud, se notifica al almacenista por correo, WhatsApp y alerta visual en la campanita.
6. **Regla de negocio:** Las solicitudes de cotización solo se desencadenan cuando el trabajo es realizado por personal técnico interno; si el trabajo lo realiza un tercero, el sistema bloquea la solicitud.
7. **Ítems fuera de oferta:** Los repuestos fuera de la oferta económica o del contrato se resaltan en amarillo para su cotización o adición a la OTe.
8. **Alimentación de la propuesta comercial:** La cotización registrada alimenta la propuesta comercial/cotización que se envía a la entidad.

### Criterios UX / Usabilidad

1. **Mínimo de clics (≤ 2 clics):** seleccionar los repuestos precargados y enviar; la solicitud se genera sin reescribir datos.
2. **Autocompletado:** entidad, placa y repuestos se precargan desde la OTi y el diagnóstico.
3. **Confirmación en tiempo real:** el envío y el cambio de estado se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Crear la solicitud con datos precargados (caso feliz)**

Dado que existe una OTi con diagnóstico y repuestos a cotizar
Cuando el Coordinador abre el formulario de solicitud de cotización
Entonces el sistema precarga automáticamente la entidad, la placa y los repuestos a cotizar.

**Escenario 2: Enviar la solicitud al almacenista (caso feliz)**

Dado que el Coordinador seleccionó los repuestos a cotizar
Cuando envía la solicitud
Entonces el sistema notifica al almacenista por correo, WhatsApp y alerta visual, y registra la solicitud en estado pendiente.

**Escenario 3: Consultar el estado de la solicitud (caso feliz)**

Dado que existe una solicitud de cotización enviada
Cuando el Coordinador consulta su estado
Entonces el sistema muestra el estado actual: pendiente, en proceso o respondida.

**Escenario 4: Registrar la respuesta de cotización (caso feliz)**

Dado que el almacenista respondió la solicitud
Cuando el Coordinador registra la cotización recibida
Entonces la solicitud pasa a estado respondida y queda enlazada a la OTi.

**Escenario 5: Bloqueo para trabajo realizado por terceros (excepción)**

Dado que el trabajo es realizado por un tercero (no por personal técnico interno)
Cuando el Coordinador intenta solicitar la cotización
Entonces el sistema bloquea la solicitud, porque solo aplica para trabajo de personal técnico interno.

**Escenario 6: Solicitud sin repuestos (excepción)**

Dado que no se seleccionó ningún repuesto a cotizar
Cuando el Coordinador intenta enviar la solicitud
Entonces el sistema bloquea el envío y exige seleccionar al menos un repuesto.

**Escenario 7: Ítems fuera de oferta resaltados (excepción)**

Dado que la OTi contiene repuestos fuera de la oferta económica o del contrato
Cuando el Coordinador abre el formulario de cotización
Entonces el sistema resalta dichos ítems en amarillo para su cotización o adición a la OTe.

**Escenario 8: Alimentar la propuesta comercial (caso feliz)**

Dado que la cotización fue registrada y la OTi está en estado "Aprobada para diagnóstico (pendiente de OTe)"
Cuando el Coordinador prepara la propuesta para la entidad
Entonces el sistema alimenta la propuesta comercial con los repuestos y cantidades cotizados.

### Matriz Delta de Cambios

**[ADDED]**
- Formulario digital de solicitud vinculado a la OTi.
- Autocompletado de entidad, placa y repuestos desde la OTi y el diagnóstico (con homologación de términos).
- Trazabilidad de estados de la solicitud (pendiente, en proceso, respondida).
- Notificación multicanal al almacenista (correo, WhatsApp, campanita).
- Bloqueo de solicitudes para trabajos realizados por terceros.
- Resaltado en amarillo de ítems fuera de oferta y alimentación de la propuesta comercial.

**[MODIFIED]**
- Canal de solicitud: de comunicación verbal o notas informales a registro digital centralizado.
- Información requerida: se garantiza entidad, placa y repuestos desde el primer contacto.

**[REMOVED]**
- Solicitudes verbales y notas informales sin trazabilidad.
- Historia duplicada "Aprobar recepción" (HU_002) que aparecía en el control de cambios original y corresponde a otro proceso.
