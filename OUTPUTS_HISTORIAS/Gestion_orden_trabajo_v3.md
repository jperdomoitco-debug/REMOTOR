# Gestión de orden de trabajo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Generar la Orden de Trabajo interna (OTi) desde la recepción |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Enviar la solicitud de aprobación al supervisor |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Actualizar la información de la Orden de Trabajo |  |  |  |  |  |  |  |  |  |
| HU_004 |  | Consultar las órdenes de trabajo |  |  |  |  |  |  |  |  |  |
| HU_005 |  | Consultar el historial de aprobaciones |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Generar automáticamente la OTi al registrar la recepción, enviarla al flujo de aprobación del supervisor de la entidad, actualizarla con los hallazgos y consultar su trazabilidad |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Generar obligatoriamente la OTi heredando el encabezado de la recepción, gestionar el flujo de aprobación con trazabilidad y actualizar los registros por hallazgos. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Generación automática de la OTi (sin creación manual), consecutivo por contrato que se reinicia con cada nuevo contrato y excepción de garantía. |  |  |  |

## Situación Actual

Actualmente la orden de trabajo se crea de manera manual a partir de la información recibida desde la zona de recepción, que puede llegar por chat, con un pantallazo del formato o con la entrega presencial del documento físico. El coordinador administrativo debe trasladar la información al formato de orden de trabajo en Excel, lo que consume tiempo y es susceptible a errores de digitación.

## Situación Deseada

Se desea que la Orden de Trabajo interna (OTi) se genere de manera automática al registrar la recepción del vehículo, heredando la información del documento de recepción. Se aclara el flujo de órdenes de trabajo: la Orden de Trabajo externa (OTe) no es obligatoria; la OTi sí lo es. La OTi recibe un consecutivo independiente por cada contrato o entidad, que se reinicia a cero con cada nuevo contrato.

---

## HU_001 — Generar la Orden de Trabajo interna (OTi) desde la recepción

**Como** Coordinador administrativo,
**Quiero** que el sistema genere automáticamente la Orden de Trabajo interna al registrar la recepción de un vehículo,
**Para** contar con la orden disponible sin diligenciamiento manual y evitar errores de digitación.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir un documento de recepción registrado en el sistema.
**3.** El vehículo asociado debe estar registrado y validado.

### Especificación Técnica de Comportamiento

**1.** **Generación automática:** Al crear la recepción, el sistema genera automáticamente la OTi, heredando el encabezado: placa, entidad, kilometraje, fecha de ingreso y corte.
**2.** **Obligatoriedad:** La OTi es obligatoria para el proceso; la OTe no lo es.
**3.** **Consecutivo por contrato:** La OTi recibe un consecutivo independiente por cada contrato o entidad, distinto del consecutivo global de la recepción. Al crear un nuevo contrato, el consecutivo de las órdenes internas se reinicia a cero y pertenece de manera exclusiva a una sola entidad.
**4.** **Estado inicial según flujo:**
   - **Con OTe:** la OTi queda en estado "Autorizada para diagnóstico y confirmación".
   - **Sin OTe:** la OTi queda en estado "Pendiente de diagnóstico", con los ítems vacíos para el diagnóstico del jefe de taller.
**5.** **Excepción por garantía:** Los ingresos por garantía no generan OTi automática; se manejan mediante un indicador o checkbox específico.
**6.** **Homologación pendiente:** Las líneas de la OTi se completan posteriormente con la homologación de términos y los hallazgos del diagnóstico.

### Criterios UX / Usabilidad

**1.** **Generación sin intervención:** el Coordinador no crea la OTi manualmente; la orden aparece disponible al registrar la recepción.
**2.** **Autocompletado:** el encabezado de la OTi se precarga con los datos de la recepción.
**3.** **Confirmación en tiempo real:** el sistema confirma la generación de la OTi y su estado inicial sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Generar automáticamente la OTi al registrar la recepción (caso feliz)**

**Dado que** se registra la recepción de un vehículo
**Cuando** el sistema confirma la recepción
**Entonces** genera automáticamente la OTi asociada, sin intervención manual del Coordinador.

**Escenario 2: Heredar el encabezado de la recepción (caso feliz)**

**Dado que** el sistema genera la OTi
**Cuando** precarga el encabezado
**Entonces** hereda de la recepción la placa, la entidad, el kilometraje, la fecha de ingreso y el corte.

**Escenario 3: Asignar el consecutivo por contrato (caso feliz)**

**Dado que** se genera una nueva OTi
**Cuando** el sistema la registra
**Entonces** asigna un consecutivo independiente por contrato o entidad, distinto del consecutivo global de la recepción.

**Escenario 4: Reiniciar el consecutivo con un nuevo contrato (caso feliz)**

**Dado que** se crea un nuevo contrato
**Cuando** el sistema genera las órdenes internas de ese contrato
**Entonces** reinicia el consecutivo a cero y lo asigna de manera exclusiva a esa entidad.

**Escenario 5: Estado inicial con orden externa (caso feliz)**

**Dado que** la recepción tiene orden externa
**Cuando** el sistema genera la OTi
**Entonces** la OTi queda en estado "Autorizada para diagnóstico y confirmación".

**Escenario 6: Estado inicial sin orden externa (caso feliz)**

**Dado que** la recepción no tiene orden externa
**Cuando** el sistema genera la OTi
**Entonces** la OTi queda en estado "Pendiente de diagnóstico", con los ítems vacíos.

**Escenario 7: Ingreso por garantía sin OTi automática (excepción)**

**Dado que** el vehículo ingresa por garantía
**Cuando** se registra la recepción con el indicador de garantía
**Entonces** el sistema no genera la OTi automática.

### Matriz Delta de Cambios

**[ADDED]**
- Consecutivo por contrato o entidad, reiniciado a cero con cada nuevo contrato y exclusivo de una sola entidad.
- Excepción de garantía: ingreso sin generación automática de la OTi, mediante indicador o checkbox.

**[MODIFIED]**
- Creación: de manual a automática, al registrar la recepción del vehículo.
- Estado sin OTe: "Pendiente de diagnóstico" (antes "Aprobada para diagnóstico (pendiente de OTe)"), en coherencia con la eliminación de la aprobación de recepciones.

**[REMOVED]**
- Creación manual de la OTi desde el sistema.
- Consecutivo único global de la OTi (ahora es por contrato).
- Traslado manual de la información desde el documento físico o Excel.

---

## HU_002 — Enviar la solicitud de aprobación al supervisor de la entidad

**Como** Coordinador administrativo,
**Quiero** enviar la solicitud de aprobación de la orden de trabajo al supervisor de la entidad desde la propia orden,
**Para** conservar la trazabilidad de las aprobaciones totales, parciales, rechazos y sus motivos, que hoy se pierden en WhatsApp.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una OTi con su información preparada.
**3.** Debe estar configurado el correo del supervisor indicado por la entidad.

### Especificación Técnica de Comportamiento

**1.** **Envío formal:** Desde la OTi se envía la solicitud de aprobación al correo indicado por la entidad para dicho fin.
**2.** **Evidencia de respuesta:** El Coordinador adjunta la evidencia fotográfica del correo y su respuesta, registrando el resultado: aprobada, rechazada o aprobada parcialmente.
**3.** **Trazabilidad de resultados:** Se registra el motivo de los rechazos y la identificación de ítems OK/NO en aprobaciones parciales.
**4.** **Reenvíos múltiples:** Una OTi puede enviarse al flujo de aprobación varias veces, principalmente cuando se añaden nuevos ítems por nuevos hallazgos del diagnóstico.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** botón "Enviar a aprobación" desde la OTi.
**2.** **Previsualización:** la OTi se muestra lista para revisar antes de enviar.
**3.** **Confirmación en tiempo real:** el envío y el registro de la evidencia se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Enviar la solicitud de aprobación (caso feliz)**

**Dado que** la OTi está preparada en su totalidad
**Cuando** el Coordinador pulsa "Enviar a aprobación"
**Entonces** el sistema envía la solicitud al correo indicado por la entidad y registra el envío en el historial.

**Escenario 2: Registrar la respuesta del supervisor (caso feliz)**

**Dado que** se recibió la respuesta del supervisor
**Cuando** el Coordinador adjunta la evidencia fotográfica del correo y su respuesta
**Entonces** el sistema registra el resultado como aprobada, rechazada o aprobada parcialmente.

**Escenario 3: Reenviar por nuevos hallazgos (caso feliz)**

**Dado que** se añadieron nuevos ítems por hallazgos del diagnóstico
**Cuando** el Coordinador envía nuevamente la OTi a aprobación
**Entonces** el sistema permite el reenvío y conserva el historial de cada envío.

**Escenario 4: Rechazo con motivo (excepción)**

**Dado que** el supervisor rechaza la orden
**Cuando** el Coordinador registra el rechazo y su motivo
**Entonces** la OTi queda en estado rechazado con el motivo visible para su ajuste.

**Escenario 5: Aprobación parcial (excepción)**

**Dado que** el supervisor aprueba parcialmente la orden
**Cuando** el Coordinador registra la respuesta
**Entonces** el sistema identifica y muestra los ítems OK y los ítems NO de la aprobación parcial.

### Matriz Delta de Cambios

**[ADDED]**
- Envío de la solicitud desde la OTi al correo de la entidad.
- Registro del resultado (aprobada, rechazada, aprobada parcialmente) con motivo.
- Historial de reenvíos múltiples por nuevos ítems.
- Adjunto de evidencia fotográfica del correo y su respuesta.

**[MODIFIED]**
- Canal de aprobación: de WhatsApp informal a correo formal con evidencia registrada en la OTi.
- Criterios de aceptación consolidados a nivel de negocio.

**[REMOVED]**
- Pérdida de trazabilidad de las aprobaciones, rechazos y motivos en el chat de WhatsApp.

---

## HU_003 — Actualizar la información de la Orden de Trabajo

**Como** Coordinador administrativo,
**Quiero** actualizar la OTi con los nuevos hallazgos del diagnóstico,
**Para** mantener la orden actualizada y lista para su envío al flujo de aprobación.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir un diagnóstico (inicial o adicional) asociado a la OTi.
**3.** La OTi debe estar en estado editable (no enviada o pendiente de ajustes).

### Especificación Técnica de Comportamiento

**1.** **Actualización por diagnóstico:** Al crearse un nuevo diagnóstico, se actualiza la OTi agregando los nuevos elementos. Ante un repuesto o elemento adicional se genera un diagnóstico adicional o versión nueva, sin eliminar el diagnóstico inicial.
**2.** **Ítems fuera de oferta:** Los repuestos o trabajos fuera de la oferta económica o del contrato se resaltan en amarillo y se envían a coordinación para gestionar su autorización previa o adición a la OTe.
**3.** **Ajuste administrativo:** La orden siempre permite ajustarse desde el área administrativa antes de enviarse al flujo de aprobación.
**4.** **Protocolo de detención por adicionales:**
   - **Caso A (independiente):** el adicional no afecta lo aprobado; el vehículo continúa en reparación y el adicional queda "pendiente" para una nueva OTe, notificando a coordinación.
   - **Caso B (dependiente/crítico):** el Coordinador marca el checkbox "Requiere Pausa por Dependencia Técnica"; la OTi cambia a "Pausado por adicional pendiente", se detiene el cronómetro del mecánico y se notifica urgentemente a coordinación.
**5.** **Reactivación automática:** Al cargar la OTe aprobada, la OTi pasa de "Pausado" a "Autorizado/En ejecución" y notifica al jefe de taller para reanudar.

### Criterios UX / Usabilidad

**1.** **Marca visual:** los ítems fuera de oferta se resaltan en amarillo para su identificación inmediata.
**2.** **Confirmación en tiempo real:** la actualización de la OTi y el cambio de estado se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Marcar ítems fuera de la oferta (caso feliz)**

**Dado que** el diagnóstico contiene repuestos o trabajos fuera del contrato u oferta vigente
**Cuando** el Coordinador actualiza la OTi
**Entonces** el sistema resalta dichos ítems en amarillo para gestionar su autorización o adición a la OTe.

**Escenario 2: Ajustar la OTi antes de enviar a aprobación (caso feliz)**

**Dado que** la OTi está en estado editable
**Cuando** el Coordinador realiza ajustes en la orden
**Entonces** el sistema permite modificarla desde el área administrativa antes de enviarla al flujo de aprobación.

**Escenario 3: Generar un diagnóstico adicional sin eliminar el inicial (caso feliz)**

**Dado que** se detecta un repuesto o elemento adicional durante la ejecución
**Cuando** el jefe de taller genera un nuevo diagnóstico
**Entonces** el sistema crea un diagnóstico adicional vinculado a la OTi, sin eliminar el diagnóstico inicial.

**Escenario 4: Adicional independiente que no detiene la reparación (excepción)**

**Dado que** se registra un diagnóstico adicional que no afecta lo ya aprobado
**Cuando** el Coordinador guarda el adicional sin marcar pausa
**Entonces** el vehículo continúa en reparación, el adicional queda "pendiente" para una nueva OTe y se notifica a coordinación.

**Escenario 5: Adicional dependiente que pausa la OTi (excepción)**

**Dado que** el Coordinador marca el checkbox "Requiere Pausa por Dependencia Técnica"
**Cuando** guarda el diagnóstico adicional
**Entonces** la OTi cambia a "Pausado por adicional pendiente", se detiene el cronómetro del mecánico y se notifica urgentemente a coordinación.

**Escenario 6: Reactivación automática de la OTi (caso feliz)**

**Dado que** se carga la OTe aprobada sobre una OTi pausada
**Cuando** el sistema confirma la carga
**Entonces** la OTi pasa a "Autorizado/En ejecución" y notifica al jefe de taller para reanudar el trabajo.

### Matriz Delta de Cambios

**[ADDED]**
- Regla de diagnóstico adicional o versión nueva, sin eliminar el diagnóstico inicial.
- Resaltado en amarillo de ítems fuera de oferta o contrato.
- Protocolo de detención con checkbox "Requiere Pausa por Dependencia Técnica" (Caso A continúa, Caso B pausa).
- Reactivación automática de la OTi al cargar la OTe aprobada.

**[MODIFIED]**
- Actualización de la OTi con los nuevos hallazgos del diagnóstico.
- Criterios de aceptación consolidados a nivel de negocio.

**[REMOVED]**
- Transcripción y traducción del documento de diagnóstico o comunicación verbal de hallazgos.

---

## HU_004 — Consultar las órdenes de trabajo

**Como** Coordinador administrativo,
**Quiero** consultar el listado de todas las órdenes de trabajo,
**Para** tener trazabilidad de las guardadas sin enviar y de las que ya cumplieron su ciclo de ejecución.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Deben existir OTi registradas en el sistema.

### Especificación Técnica de Comportamiento

**1.** **Listado completo:** El sistema muestra todas las OTi, distinguiendo las que están guardadas y no han sido enviadas a aprobación, de las que ya cumplieron su ciclo de ejecución.
**2.** **Búsqueda estricta:** La búsqueda se realiza por placa o sigla; no se admite búsqueda por entidad ni por contrato.
**3.** **Filtros:** Permite filtrar por estado y fecha.
**4.** **Detalle:** Al seleccionar una OTi, se muestra su detalle completo.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** un clic abre el detalle de la OTi desde el listado.
**2.** **Autocompletado y precarga:** el listado se precarga con placa, entidad, fecha, estado y consecutivo.
**3.** **Confirmación en tiempo real:** búsqueda y filtros asíncronos, sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Listar todas las órdenes de trabajo (caso feliz)**

**Dado que** el Coordinador está autenticado y existen OTi registradas
**Cuando** abre el listado de órdenes de trabajo
**Entonces** el sistema muestra todas las OTi con placa, entidad, fecha, estado y consecutivo.

**Escenario 2: Distinguir guardadas y ejecutadas (caso feliz)**

**Dado que** el listado de OTi está visible
**Cuando** el Coordinador revisa los estados
**Entonces** el sistema distingue las OTi guardadas sin enviar de las que ya cumplieron su ciclo de ejecución.

**Escenario 3: Buscar una OTi por placa o sigla (caso feliz)**

**Dado que** el Coordinador desea localizar una OTi
**Cuando** digita la placa o sigla y confirma la búsqueda
**Entonces** el sistema filtra y muestra únicamente la OTi correspondiente.

**Escenario 4: Filtrar por estado (caso feliz)**

**Dado que** el listado de OTi está visible
**Cuando** el Coordinador selecciona un estado en el filtro
**Entonces** el sistema muestra únicamente las OTi con ese estado, sin recargar la pantalla.

**Escenario 5: Sin resultados de búsqueda (excepción)**

**Dado que** la placa o sigla digitada no coincide con ninguna OTi
**Cuando** el Coordinador confirma la búsqueda
**Entonces** el sistema muestra el estado vacío "No se encontraron órdenes de trabajo".

### Matriz Delta de Cambios

**[ADDED]**
- Búsqueda estricta por placa o sigla.
- Filtros en línea por estado y fecha.
- Distinción entre OTi guardadas sin enviar y OTi ejecutadas.

**[MODIFIED]**
- Consulta de trazabilidad digital de las OTi en un listado único.
- Criterios de aceptación consolidados a nivel de negocio.

**[REMOVED]**
- Búsqueda de OTi por entidad o por contrato.

---

## HU_005 — Consultar el historial de aprobaciones

**Como** Coordinador administrativo,
**Quiero** consultar el historial de aprobaciones de una orden de trabajo,
**Para** obtener trazabilidad de cada envío: fecha, resultado, ítems OK/NO y soportes adjuntos.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una OTi con historial de envíos de aprobación.

### Especificación Técnica de Comportamiento

**1.** **Historial por envío:** El sistema muestra cada envío de aprobación con su fecha, resultado (aprobado, rechazado, aprobado parcialmente), ítems OK/NO y soportes adjuntos.
**2.** **Orden cronológico:** Los envíos se muestran ordenados cronológicamente.
**3.** **Solo lectura:** El historial es de consulta y no permite edición.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** un clic despliega el historial desde la OTi.
**2.** **Autocompletado y precarga:** los registros del historial se precargan con fecha, resultado e ítems.
**3.** **Confirmación en tiempo real:** la carga del historial es asíncrona, sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Consultar el historial de aprobaciones (caso feliz)**

**Dado que** existe una OTi con envíos de aprobación registrados
**Cuando** el Coordinador abre el historial de la OTi
**Entonces** el sistema muestra cada envío con fecha, resultado y soportes adjuntos.

**Escenario 2: Visualizar el detalle de un envío (caso feliz)**

**Dado que** el historial está visible
**Cuando** el Coordinador selecciona un envío
**Entonces** el sistema muestra su detalle: resultado, motivo (si aplica) y la evidencia fotográfica adjunta.

**Escenario 3: Ítems OK/NO en aprobación parcial (caso feliz)**

**Dado que** un envío fue aprobado parcialmente
**Cuando** el Coordinador consulta su detalle
**Entonces** el sistema muestra los ítems OK y los ítems NO de esa aprobación parcial.

**Escenario 4: Historial vacío (excepción)**

**Dado que** la OTi no ha sido enviada a aprobación
**Cuando** el Coordinador abre el historial
**Entonces** el sistema muestra el estado vacío "Esta orden aún no tiene envíos de aprobación".

### Matriz Delta de Cambios

**[ADDED]**
- Detalle por envío con ítems OK/NO y soportes adjuntos.
- Orden cronológico del historial.
- Estado vacío para OTi sin envíos.

**[MODIFIED]**
- Trazabilidad de aprobaciones ahora registrada y consultable en el sistema.
- Criterios de aceptación consolidados a nivel de negocio.

**[REMOVED]**
- Aprobaciones sin registro ni soporte (proceso informal por WhatsApp).
