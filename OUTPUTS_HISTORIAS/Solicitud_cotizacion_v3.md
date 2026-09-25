# Solicitud de cotización

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Solicitar la cotización de repuestos |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Estandarizar la solicitud de cotizaciones al almacenista mediante un formulario digital vinculado a la Orden de Trabajo interna (OTi) |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Vincular una solicitud digital a la OTi con autocompletado de entidad, placa y repuestos, trazabilidad de estados y notificación al almacenista. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Consolidar criterios de aceptación a nivel de negocio, estandarizar la nomenclatura OTe/OTi y referenciar el módulo transversal de notificaciones. |  |  |  |

## Situación Actual

La solicitud de cotizaciones se realiza actualmente de forma verbal o mediante notas informales entre el área administrativa y la encargada de inventario. Este proceso carece de trazabilidad, estandarización y registro centralizado, lo que genera interrupciones operativas, falta de visibilidad sobre el estado de las solicitudes y tiempos de respuesta ineficientes por la dependencia de la interacción manual.

## Situación Deseada

Implementar un proceso estandarizado y digital para la solicitud y gestión de cotizaciones de repuestos, reemplazando los canales informales por una plataforma de registro centralizado que garantice la trazabilidad de cada requerimiento desde su origen hasta la respuesta final. El flujo asegura que todas las solicitudes incluyan la información necesaria desde el primer contacto (entidad, placa y repuestos a cotizar), evitando reprocesos y proporcionando visibilidad en tiempo real del estado de cada gestión.

---

## HU_001 — Solicitar la cotización de repuestos

**Como** Coordinador administrativo,
**Quiero** solicitar cotizaciones de repuestos mediante un formulario digital vinculado a la Orden de Trabajo interna (OTi),
**Para** centralizar la información, eliminar reprocesos y garantizar un seguimiento efectivo de cada requerimiento.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una OTi vinculada con el diagnóstico y los repuestos a cotizar.
**3.** El trabajo debe ser realizado por **personal técnico interno** (regla de negocio: no aplica cuando el trabajo lo ejecuta un tercero).

### Especificación Técnica de Comportamiento

**1.** **Formulario vinculado a la OTi:** La solicitud de cotización se genera desde un formulario asociado a la Orden de Trabajo interna.
**2.** **Autocompletado:** Al abrir el formulario, se precargan en solo lectura la entidad, la placa y los repuestos a cotizar desde la OTi y el diagnóstico.
**3.** **Envío al almacenista:** La solicitud se envía con la información completa para que el almacenista realice una cotización efectiva.
**4.** **Trazabilidad de estados:** Cada solicitud registra su estado (pendiente, en proceso, respondida) y queda enlazada a la OTi.
**5.** **Notificación multicanal:** Al enviar la solicitud, el módulo transversal notifica al almacenista por correo, WhatsApp y alerta visual en la campanita.
**6.** **Regla de negocio:** Las solicitudes de cotización solo se desencadenan cuando el trabajo es realizado por personal técnico interno; si lo realiza un tercero, el sistema bloquea la solicitud.
**7.** **Ítems fuera de oferta:** Los repuestos fuera de la oferta económica o del contrato se resaltan en amarillo para su cotización o adición a la OTe.
**8.** **Alimentación de la propuesta comercial:** La cotización registrada alimenta la propuesta comercial que se envía a la entidad.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** seleccionar los repuestos precargados y enviar; la solicitud se genera sin reescribir datos.
**2.** **Autocompletado:** entidad, placa y repuestos se precargan desde la OTi y el diagnóstico.
**3.** **Confirmación en tiempo real:** el envío y el cambio de estado se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Crear la solicitud con datos precargados (caso feliz)**

**Dado que** existe una OTi con diagnóstico y repuestos a cotizar
**Cuando** el Coordinador abre el formulario de solicitud de cotización
**Entonces** el sistema precarga automáticamente la entidad, la placa y los repuestos a cotizar.

**Escenario 2: Enviar la solicitud al almacenista (caso feliz)**

**Dado que** el Coordinador seleccionó los repuestos a cotizar
**Cuando** envía la solicitud
**Entonces** el módulo transversal notifica al almacenista por correo, WhatsApp y campanita, y la solicitud queda en estado pendiente.

**Escenario 3: Consultar el estado de la solicitud (caso feliz)**

**Dado que** existe una solicitud de cotización enviada
**Cuando** el Coordinador consulta su estado
**Entonces** el sistema muestra el estado actual: pendiente, en proceso o respondida.

**Escenario 4: Registrar la respuesta de cotización (caso feliz)**

**Dado que** el almacenista respondió la solicitud
**Cuando** el Coordinador registra la cotización recibida
**Entonces** la solicitud pasa a estado respondida y queda enlazada a la OTi.

**Escenario 5: Bloqueo para trabajo realizado por terceros (excepción)**

**Dado que** el trabajo es realizado por un tercero y no por personal técnico interno
**Cuando** el Coordinador intenta solicitar la cotización
**Entonces** el sistema bloquea la solicitud, porque solo aplica para trabajo de personal técnico interno.

**Escenario 6: Solicitud sin repuestos (excepción)**

**Dado que** no se seleccionó ningún repuesto a cotizar
**Cuando** el Coordinador intenta enviar la solicitud
**Entonces** el sistema bloquea el envío y exige seleccionar al menos un repuesto.

**Escenario 7: Ítems fuera de oferta resaltados (excepción)**

**Dado que** la OTi contiene repuestos fuera de la oferta económica o del contrato
**Cuando** el Coordinador abre el formulario de cotización
**Entonces** el sistema resalta dichos ítems en amarillo para su cotización o adición a la OTe.

**Escenario 8: Alimentar la propuesta comercial (caso feliz)**

**Dado que** la cotización fue registrada y la OTi está a la espera de la oferta para la entidad
**Cuando** el Coordinador prepara la propuesta para la entidad
**Entonces** el sistema alimenta la propuesta comercial con los repuestos y cantidades cotizados.

### Matriz Delta de Cambios

**[ADDED]**
- Referencia explícita al módulo transversal de notificaciones para comunicar al almacenista.

**[MODIFIED]**
- Estado de la OTi citado en los escenarios, ajustado a la nomenclatura vigente (sin referencias a la aprobación de la recepción).
- Criterios de aceptación consolidados a nivel de negocio, sin escenarios de prueba detallados.

**[REMOVED]**
- Referencias al estado "Aprobada para diagnóstico (pendiente de OTe)" en el flujo de cotización.
