# Gestión de orden de trabajo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Crear la Orden de Trabajo interna (OTi) desde la recepción |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Enviar la solicitud de aprobación al supervisor |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Actualizar la información de la Orden de Trabajo |  |  |  |  |  |  |  |  |  |
| HU_004 |  | Consultar las órdenes de trabajo |  |  |  |  |  |  |  |  |  |
| HU_005 |  | Consultar el historial de aprobaciones |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Crear la OTi al registrarse la recepción, enviarla al flujo de aprobación del supervisor de la entidad, actualizarla con los hallazgos y consultar su trazabilidad |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Crear la orden de trabajo al momento de que se registre la recepción de un vehículo |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Transformación a versión 2.0: OTi obligatoria con encabezado heredado de la recepción, flujo de aprobación con trazabilidad, actualización por hallazgos con protocolo de pausa y consultas de trazabilidad |  |  |  |

## Situación Actual

Actualmente la orden de trabajo se crea de manera manual a partir de la información recibida desde la zona de recepción, que puede llegar por chat, con un pantallazo del formato o con la entrega presencial del documento físico. El coordinador administrativo debe trasladar manualmente la información desde el documento de recepción al formato de orden de trabajo en Excel, lo que consume tiempo y es susceptible a errores de digitación.

## Situación Deseada

Se desea que la creación de las órdenes de trabajo se ejecute de manera automática al registrarse una nueva recepción de vehículo, heredando la información del documento de recepción. Queda como trabajo pendiente la especificación de los detalles de la orden según la entidad. Además se aclara el flujo de órdenes de trabajo: **la Orden de Trabajo externa (OTe) no es obligatoria; la Orden de Trabajo interna (OTi) sí lo es**, y es la OTi la que se crea, actualiza y envía a aprobación.

---

## HU_001 — Crear la Orden de Trabajo interna (OTi) desde la recepción

**Como** Coordinador administrativo,
**Quiero** que el sistema cree automáticamente la Orden de Trabajo interna al registrarse la recepción de un vehículo, con opción de creación manual,
**Para** reducir el trabajo manual y los errores de digitación al trasladar la información de la recepción.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir un documento de recepción registrado en el sistema.
3. El vehículo asociado debe estar registrado y validado.

### Especificación Técnica de Comportamiento

1. **Creación automática:** Al registrarse una recepción, el sistema crea automáticamente la **OTi** heredando el encabezado: placa, entidad, kilometraje, fecha de ingreso, corte y un **consecutivo único global**.
2. **Creación manual:** El sistema permite crear OTi manualmente, siempre que se relacione obligatoriamente con un documento de recepción.
3. **Obligatoriedad:** La OTi es obligatoria para el proceso; la OTe no lo es.
4. **Estado inicial según flujo:**
   - Con OTe: la OTi queda en estado **"Autorizada para diagnóstico y confirmación"**.
   - Sin OTe: la OTi queda en estado **"Aprobada para diagnóstico (pendiente de OTe)"**.
5. **Homologación pendiente:** Las líneas de la OTi se completan posteriormente con la homologación de términos y los hallazgos del diagnóstico.

### Criterios UX / Usabilidad

1. **Mínimo de clics (0 clics):** la OTi se crea automáticamente al registrarse la recepción, sin intervención manual.
2. **Autocompletado:** el encabezado de la OTi se precarga con los datos de la recepción.
3. **Confirmación en tiempo real:** el sistema confirma la creación de la OTi y su estado inicial sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Crear la OTi automáticamente al registrarse la recepción (caso feliz)**

Dado que se registra un nuevo documento de recepción
Cuando el sistema confirma el registro de la recepción
Entonces crea automáticamente la OTi con el encabezado heredado: placa, entidad, kilometraje, fecha, corte y consecutivo único.

**Escenario 2: Crear la OTi manualmente vinculada a una recepción (caso feliz)**

Dado que se requiere crear una orden de trabajo de forma manual
Cuando el Coordinador crea la OTi
Entonces el sistema la relaciona obligatoriamente con un documento de recepción existente.

**Escenario 3: Bloqueo de creación manual sin recepción (excepción)**

Dado que no existe un documento de recepción asociado
Cuando el Coordinador intenta crear una OTi manual
Entonces el sistema bloquea la creación y exige vincular un documento de recepción.

**Escenario 4: Estado inicial con orden externa (caso feliz)**

Dado que la recepción tiene orden externa cargada
Cuando el sistema crea la OTi
Entonces la OTi queda en estado "Autorizada para diagnóstico y confirmación".

**Escenario 5: Estado inicial sin orden externa (caso feliz)**

Dado que la recepción no tiene orden externa
Cuando el sistema crea la OTi
Entonces la OTi queda en estado "Aprobada para diagnóstico (pendiente de OTe)".

**Escenario 6: Consecutivo único global (caso feliz)**

Dado que se crea una nueva OTi
Cuando el sistema la registra
Entonces asigna un consecutivo único global, sin numeraciones independientes por entidad.

### Matriz Delta de Cambios

**[ADDED]**
- Creación automática de la OTi con encabezado heredado y consecutivo único global.
- Estados iniciales de la OTi según el flujo: "Autorizada para diagnóstico y confirmación" (con OTe) y "Aprobada para diagnóstico (pendiente de OTe)" (sin OTe).
- Bloqueo de la creación manual sin documento de recepción asociado.

**[MODIFIED]**
- Creación manual: ahora condicionada a relacionarse obligatoriamente con una recepción.
- Herencia de datos de la recepción al encabezado de la OTi.

**[REMOVED]**
- Traslado manual de la información desde el documento físico o Excel al formato de orden de trabajo.

---

## HU_002 — Enviar la solicitud de aprobación al supervisor de la entidad

**Como** Coordinador administrativo,
**Quiero** enviar la solicitud de aprobación de la orden de trabajo al supervisor de la entidad desde la propia orden,
**Para** conservar la trazabilidad de las aprobaciones totales, parciales, rechazos y sus motivos, que hoy se pierden en WhatsApp.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una OTi con su información preparada.
3. Debe estar configurado el correo del supervisor indicado por la entidad.

### Especificación Técnica de Comportamiento

1. **Envío formal:** Desde la OTi se envía la solicitud de aprobación al correo indicado por la entidad para dicho fin.
2. **Evidencia de respuesta:** La coordinadora adjunta la evidencia fotográfica del correo y su respuesta, registrando el resultado: **aprobada**, **rechazada** o **aprobada parcialmente**.
3. **Trazabilidad de resultados:** Se registra el motivo de rechazos y la identificación de ítems OK/NO en aprobaciones parciales.
4. **Reenvíos múltiples:** Una OTi puede enviarse al flujo de aprobación varias veces, principalmente cuando se añaden nuevos ítems por nuevos hallazgos del diagnóstico.

### Criterios UX / Usabilidad

1. **Mínimo de clics (1 clic):** botón "Enviar a aprobación" desde la OTi.
2. **Previsualización:** la OTi se muestra lista para revisar antes de enviar.
3. **Confirmación en tiempo real:** el envío y el registro de la evidencia se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Enviar la solicitud de aprobación (caso feliz)**

Dado que la OTi está preparada en su totalidad
Cuando el Coordinador pulsa "Enviar a aprobación"
Entonces el sistema envía la solicitud al correo indicado por la entidad y registra el envío en el historial.

**Escenario 2: Registrar la respuesta del supervisor (caso feliz)**

Dado que se recibió la respuesta del supervisor
Cuando el Coordinador adjunta la evidencia fotográfica del correo y su respuesta
Entonces el sistema registra el resultado como aprobada, rechazada o aprobada parcialmente.

**Escenario 3: Reenviar por nuevos hallazgos (caso feliz)**

Dado que se añadieron nuevos ítems por hallazgos del diagnóstico
Cuando el Coordinador envía nuevamente la OTi a aprobación
Entonces el sistema permite el reenvío y conserva el historial de cada envío.

**Escenario 4: Rechazo con motivo (excepción)**

Dado que el supervisor rechaza la orden
Cuando el Coordinador registra el rechazo y su motivo
Entonces la OTi queda en estado rechazado con el motivo visible para su ajuste.

**Escenario 5: Aprobación parcial (excepción)**

Dado que el supervisor aprueba parcialmente la orden
Cuando el Coordinador registra la respuesta
Entonces el sistema identifica y muestra los ítems OK y los ítems NO de la aprobación parcial.

### Matriz Delta de Cambios

**[ADDED]**
- Envío de la solicitud desde la OTi al correo de la entidad.
- Registro del resultado (aprobada, rechazada, aprobada parcialmente) con motivo.
- Historial de reenvíos múltiples por nuevos ítems.
- Adjunto de evidencia fotográfica del correo y su respuesta.

**[MODIFIED]**
- Canal de aprobación: de WhatsApp informal a correo formal con evidencia registrada en la OTi.

**[REMOVED]**
- Pérdida de trazabilidad de las aprobaciones, rechazos y motivos en el chat de WhatsApp.

---

## HU_003 — Actualizar la información de la Orden de Trabajo

**Como** Coordinador administrativo,
**Quiero** actualizar la OTi con los nuevos hallazgos del diagnóstico, homologando los términos del taller con los de la entidad,
**Para** mantener la orden alineada y lista para su envío al flujo de aprobación.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir un diagnóstico (inicial o adicional) asociado a la OTi.
3. La OTi debe estar en estado editable (no enviada o pendiente de ajustes).

### Especificación Técnica de Comportamiento

1. **Homologación de términos:** El sistema realiza la homologación de los términos que maneja el taller con los que maneja la entidad al incorporar los hallazgos.
2. **Actualización por diagnóstico:** Al crearse un nuevo diagnóstico, se actualiza la OTi agregando los nuevos elementos; una OTi puede tener N diagnósticos y los nuevos hallazgos se registran como registros adicionales, sin sobrescribir los anteriores.
3. **Ítems fuera de oferta:** Los repuestos o trabajos fuera de la oferta económica o del contrato se resaltan en **amarillo** y se envían a coordinación para gestionar su autorización previa o adición a la OTe.
4. **Ajuste administrativo:** La orden siempre permite ajustarse desde el área administrativa antes de enviarse al flujo de aprobación.
5. **Protocolo de detención por adicionales:**
   - Caso A (independiente): el adicional no afecta lo aprobado; el vehículo **continúa** en reparación y el adicional queda "pendiente" para una nueva OTe, notificando a coordinación.
   - Caso B (dependiente/crítico): el Coordinador marca el checkbox **"Requiere Pausa por Dependencia Técnica"**; la OTi cambia a **"Pausado por adicional pendiente"**, se detiene el cronómetro del mecánico y se notifica urgentemente a coordinación.
6. **Reactivación automática:** Al cargar la OTe aprobada, la OTi pasa de "Pausado" a **"Autorizado/En ejecución"** y notifica al jefe de taller para reanudar.

### Criterios UX / Usabilidad

1. **Autocompletado:** los nuevos ítems se precargan desde el diagnóstico, evitando la transcripción manual.
2. **Marca visual:** los ítems fuera de oferta se resaltan en amarillo para su identificación inmediata.
3. **Confirmación en tiempo real:** la actualización de la OTi y el cambio de estado se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Homologar términos y actualizar la OTi (caso feliz)**

Dado que se crea un nuevo documento de diagnóstico
Cuando el Coordinador homologa los términos del taller con los de la entidad
Entonces la OTi se actualiza agregando los nuevos elementos del diagnóstico.

**Escenario 2: Marcar ítems fuera de la oferta (caso feliz)**

Dado que el diagnóstico contiene repuestos o trabajos fuera del contrato u oferta vigente
Cuando el Coordinador actualiza la OTi
Entonces el sistema resalta dichos ítems en amarillo para gestionar su autorización o adición a la OTe.

**Escenario 3: Ajustar la OTi antes de enviar a aprobación (caso feliz)**

Dado que la OTi está en estado editable
Cuando el Coordinador realiza ajustes en la orden
Entonces el sistema permite modificarla desde el área administrativa antes de enviarla al flujo de aprobación.

**Escenario 4: Adicional independiente que no detiene la reparación (excepción)**

Dado que se registra un diagnóstico adicional que no afecta lo ya aprobado
Cuando el Coordinador guarda el adicional sin marcar pausa
Entonces el vehículo continúa en reparación, el adicional queda "pendiente" para una nueva OTe y se notifica a coordinación.

**Escenario 5: Adicional dependiente que pausa la OTi (excepción)**

Dado que el Coordinador marca el checkbox "Requiere Pausa por Dependencia Técnica"
Cuando guarda el diagnóstico adicional
Entonces la OTi cambia a "Pausado por adicional pendiente", se detiene el cronómetro del mecánico y se notifica urgentemente a coordinación.

**Escenario 6: Reactivación automática de la OTi (caso feliz)**

Dado que se carga la OTe aprobada sobre una OTi pausada
Cuando el sistema confirma la carga
Entonces la OTi pasa a "Autorizado/En ejecución" y notifica al jefe de taller para reanudar el trabajo.

### Matriz Delta de Cambios

**[ADDED]**
- Homologación de términos entre taller y entidad.
- Resaltado en amarillo de ítems fuera de oferta o contrato.
- Protocolo de detención con checkbox "Requiere Pausa por Dependencia Técnica" (Caso A continúa, Caso B pausa).
- Reactivación automática de la OTi al cargar la OTe aprobada.

**[MODIFIED]**
- Actualización de la OTi: desde transcripción manual/verbal del diagnóstico a precarga automática de los hallazgos.
- Gestión de N diagnósticos como registros adicionales, sin sobrescribir los anteriores.

**[REMOVED]**
- Transcripción y traducción manual del documento de diagnóstico o comunicación verbal de hallazgos.

---

## HU_004 — Consultar las órdenes de trabajo

**Como** Coordinador administrativo,
**Quiero** consultar el listado de todas las órdenes de trabajo,
**Para** tener trazabilidad de las guardadas sin enviar y de las que ya cumplieron su ciclo de ejecución.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Deben existir OTi registradas en el sistema.

### Especificación Técnica de Comportamiento

1. **Listado completo:** El sistema muestra todas las OTi, distinguiendo las que están guardadas y no han sido enviadas a aprobación, de las que ya cumplieron su ciclo de ejecución.
2. **Búsqueda estricta:** La búsqueda se realiza por **placa o sigla**; no se admite búsqueda por entidad ni por contrato.
3. **Filtros:** Permite filtrar por estado y fecha.
4. **Detalle:** Al seleccionar una OTi, se muestra su detalle completo.

### Criterios UX / Usabilidad

1. **Mínimo de clics (1 clic):** un clic abre el detalle de la OTi desde el listado.
2. **Autocompletado y precarga:** el listado se precarga con placa, entidad, fecha, estado y consecutivo.
3. **Confirmación en tiempo real:** búsqueda y filtros asíncronos, sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Listar todas las órdenes de trabajo (caso feliz)**

Dado que el Coordinador está autenticado
Y existen OTi registradas
Cuando abre el listado de órdenes de trabajo
Entonces el sistema muestra todas las OTi con placa, entidad, fecha, estado y consecutivo.

**Escenario 2: Distinguir guardadas y ejecutadas (caso feliz)**

Dado que el listado de OTi está visible
Cuando el Coordinador revisa los estados
Entonces el sistema distingue las OTi guardadas sin enviar de las que ya cumplieron su ciclo de ejecución.

**Escenario 3: Buscar una OTi por placa o sigla (caso feliz)**

Dado que el Coordinador desea localizar una OTi
Cuando digita la placa o sigla y confirma la búsqueda
Entonces el sistema filtra y muestra únicamente la OTi correspondiente.

**Escenario 4: Filtrar por estado (caso feliz)**

Dado que el listado de OTi está visible
Cuando el Coordinador selecciona un estado en el filtro
Entonces el sistema muestra únicamente las OTi con ese estado, sin recargar la pantalla.

**Escenario 5: Sin resultados de búsqueda (excepción)**

Dado que la placa o sigla digitada no coincide con ninguna OTi
Cuando el Coordinador confirma la búsqueda
Entonces el sistema muestra el estado vacío "No se encontraron órdenes de trabajo".

### Matriz Delta de Cambios

**[ADDED]**
- Búsqueda estricta por placa o sigla.
- Filtros en línea por estado y fecha.
- Distinción entre OTi guardadas sin enviar y OTi ejecutadas.

**[MODIFIED]**
- Consulta de trazabilidad digital de las OTi en un listado único.

**[REMOVED]**
- Búsqueda de OTi por entidad o por contrato.

---

## HU_005 — Consultar el historial de aprobaciones

**Como** Coordinador administrativo,
**Quiero** consultar el historial de aprobaciones de una orden de trabajo,
**Para** obtener trazabilidad de cada envío: fecha, resultado, ítems OK/NO y soportes adjuntos.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una OTi con historial de envíos de aprobación.

### Especificación Técnica de Comportamiento

1. **Historial por envío:** El sistema muestra cada envío de aprobación con su fecha, resultado (aprobado, rechazado, aprobado parcialmente), ítems OK/NO y soportes adjuntos.
2. **Orden cronológico:** Los envíos se muestran ordenados cronológicamente.
3. **Solo lectura:** El historial es de consulta y no permite edición.

### Criterios UX / Usabilidad

1. **Mínimo de clics (1 clic):** un clic despliega el historial desde la OTi.
2. **Autocompletado y precarga:** los registros del historial se precargan con fecha, resultado e ítems.
3. **Confirmación en tiempo real:** la carga del historial es asíncrona, sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Consultar el historial de aprobaciones (caso feliz)**

Dado que existe una OTi con envíos de aprobación registrados
Cuando el Coordinador abre el historial de la OTi
Entonces el sistema muestra cada envío con fecha, resultado y soportes adjuntos.

**Escenario 2: Visualizar el detalle de un envío (caso feliz)**

Dado que el historial está visible
Cuando el Coordinador selecciona un envío
Entonces el sistema muestra su detalle: resultado, motivo (si aplica) y la evidencia fotográfica adjunta.

**Escenario 3: Ítems OK/NO en aprobación parcial (caso feliz)**

Dado que un envío fue aprobado parcialmente
Cuando el Coordinador consulta su detalle
Entonces el sistema muestra los ítems OK y los ítems NO de esa aprobación parcial.

**Escenario 4: Historial vacío (excepción)**

Dado que la OTi no ha sido enviada a aprobación
Cuando el Coordinador abre el historial
Entonces el sistema muestra el estado vacío "Esta orden aún no tiene envíos de aprobación".

### Matriz Delta de Cambios

**[ADDED]**
- Detalle por envío con ítems OK/NO y soportes adjuntos.
- Orden cronológico del historial.
- Estado vacío para OTi sin envíos.

**[MODIFIED]**
- Trazabilidad de aprobaciones ahora registrada y consultable en el sistema.

**[REMOVED]**
- Aprobaciones sin registro ni soporte (proceso informal por WhatsApp).
