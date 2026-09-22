# Consultar recepciones

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar recepciones |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Aprobar la recepción y crear la Orden de Trabajo interna (OTi) |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Consultar las recepciones de vehículos y aprobarlas, automatizando la creación de la Orden de Trabajo interna con la información del encabezado |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Consultar y aprobar recepciones mediante la búsqueda por placa o sigla, generar de forma automática la OTi con el encabezado precargado, gestionar los estados según la existencia de la orden externa y disparar las notificaciones correspondientes. |  |  |  |

## Situación Actual

Actualmente las recepciones deben ser comunicadas de manera presencial al coordinador administrativo: el asesor de servicio debe desplazarse hasta el área administrativa para entregar el documento diligenciado a mano. Esto hace que la continuidad del proceso de validación dependa de que la asesora llegue de manera oportuna a entregar la recepción.

## Situación Deseada

Se desea que el coordinador administrativo pueda consultar las recepciones de los vehículos desde un formulario maestro, revisar la información y realizar las validaciones correspondientes. Al aprobar una recepción, el sistema creará automáticamente la **Orden de Trabajo interna (OTi)** con los datos iniciales del encabezado (placa, entidad, kilometraje, corte, consecutivo único, etc.). Además se aclara el flujo de órdenes de trabajo: **la Orden de Trabajo externa (OTe) no es obligatoria; la Orden de Trabajo interna (OTi) sí lo es**.

---

## HU_001 — Consultar las recepciones de vehículos

**Como** Coordinador administrativo,
**Quiero** consultar las recepciones de vehículos desde un formulario maestro,
**Para** revisar la información y realizar las validaciones iniciales sin depender de la entrega presencial de documentos físicos.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Deben existir recepciones registradas por el **Asesor de servicio** en el sistema.
3. La base de datos de vehículos y entidades debe estar parametrizada.

### Especificación Técnica de Comportamiento

1. **Listado de Recepciones:** El sistema muestra una tabla de recepciones con placa/sigla, entidad, fecha y hora de ingreso, kilometraje y estado.
2. **Búsqueda estricta:** La búsqueda se realiza estrictamente por **placa o sigla**; no se admite búsqueda por entidad ni por contrato para evitar listas masivas.
3. **Detalle en solo lectura:** Al seleccionar una recepción, el sistema despliega el detalle completo: entidad, marca, clase, modelo, color, kilometraje, descripción de la falla, observaciones, inventario, daños de carrocería y la evidencia de la orden externa si aplica.
4. **Contratos informativos:** El contrato asociado se muestra como dato de solo lectura, sin usarse como filtro de búsqueda.
5. **Resaltado de recepciones sin orden:** Las recepciones creadas sin orden externa se resaltan con la etiqueta *"Sin OT vinculada"*.
6. **Vehículo no registrado:** Las recepciones de vehículos no registrados se muestran con la alerta *"Pendiente de validación administrativa"* para que coordinación complete y guarde los datos del vehículo.
7. **Acceso desde la notificación:** El coordinador puede abrir el detalle de una recepción directamente desde la alerta recibida en la campanita o el correo.

### Criterios UX / Usabilidad

1. **Mínimo de clics (≤ 2 clics):** un clic abre el detalle desde el listado o desde la notificación, sin salir del formulario maestro.
2. **Autocompletado y precarga:** el listado y el detalle se precargan con los datos capturados en la recepción, en modo solo lectura.
3. **Confirmaciones en tiempo real:** la búsqueda por placa/sigla y los filtros se ejecutan de forma asíncrona, sin recargar la pantalla.
4. **Filtros en línea:** permite filtrar por estado, fecha y placa sin recargar.

### Criterios de Aceptación

**Escenario 1: Visualizar el listado de recepciones (caso feliz)**

Dado que el Coordinador administrativo está autenticado
Y existen recepciones registradas en el sistema
Cuando abre el formulario maestro de recepciones
Entonces el sistema muestra la tabla de recepciones con placa, entidad, fecha, hora, kilometraje y estado.

**Escenario 2: Buscar una recepción por placa o sigla (caso feliz)**

Dado que el Coordinador desea localizar una recepción
Cuando digita la placa o sigla del vehículo y confirma la búsqueda
Entonces el sistema filtra y muestra únicamente la recepción correspondiente a esa placa o sigla.

**Escenario 3: Visualizar el detalle de una recepción (caso feliz)**

Dado que el listado de recepciones está visible
Cuando el Coordinador selecciona una recepción
Entonces el sistema muestra el detalle completo en solo lectura: entidad, marca, clase, modelo, color, kilometraje, falla, observaciones, inventario, daños y evidencia de la orden si aplica.

**Escenario 4: Identificar una recepción sin orden externa (caso feliz)**

Dado que existe una recepción creada sin orden externa
Cuando el Coordinador consulta el listado
Entonces el sistema resalta la recepción con la etiqueta "Sin OT vinculada".

**Escenario 5: Vehículo no registrado pendiente de validación (excepción)**

Dado que una recepción corresponde a un vehículo no registrado
Cuando el Coordinador abre su detalle
Entonces el sistema muestra los datos parciales ingresados por recepción y la alerta "Pendiente de validación administrativa" para completar y guardar el vehículo.

**Escenario 6: Notificación de nueva recepción (caso feliz)**

Dado que el Asesor de servicio guarda una nueva recepción
Cuando el sistema confirma el guardado
Entonces el Coordinador recibe una alerta en la campanita y un correo con el PDF adjunto, con acceso directo al detalle de la recepción.

**Escenario 7: Filtrar recepciones por estado (caso feliz)**

Dado que el listado de recepciones está visible
Cuando el Coordinador selecciona un estado en el filtro
Entonces el sistema muestra únicamente las recepciones con ese estado, sin recargar la pantalla.

### Matriz Delta de Cambios

**[ADDED]**
- Búsqueda y filtro estrictos por placa o sigla.
- Resaltado de recepciones sin orden externa ("Sin OT vinculada").
- Estado "Pendiente de validación administrativa" para vehículos no registrados.
- Acceso directo al detalle desde la notificación (campanita o correo).
- Filtros en línea por estado, fecha y placa.

**[MODIFIED]**
- Acceso: de entrega presencial del documento físico a consulta digital en formulario maestro.
- Detalle en solo lectura enriquecido con inventario, daños de carrocería y evidencia de la orden.
- Contrato tratado como dato informativo de solo lectura, nunca como filtro.

**[REMOVED]**
- Dependencia del desplazamiento presencial del asesor para entregar la recepción.
- Búsqueda de recepciones por entidad o por contrato.

---

## HU_002 — Aprobar la recepción y crear la Orden de Trabajo interna (OTi)

**Como** Coordinador administrativo,
**Quiero** aprobar la recepción validada y que el sistema cree automáticamente la Orden de Trabajo interna,
**Para** eliminar el diligenciamiento manual del encabezado de la orden y agilizar la gestión con el taller y la entidad.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
2. Debe existir una recepción con su información validada.
3. El vehículo de la recepción debe estar registrado y validado en el sistema (si no estaba registrado, ya fue completado y guardado por coordinación).

### Especificación Técnica de Comportamiento

1. **Aprobación:** Al pulsar "Aprobar", el sistema crea automáticamente la **OTi** con el encabezado precargado: placa, entidad, kilometraje, fecha de ingreso, corte y un **consecutivo único global**.
2. **Caso A (con OTe):** Si la recepción tiene orden externa cargada, el coordinador revisa el PDF/foto, valida la orden y aprueba; la OTi queda en estado **"Autorizada para diagnóstico y confirmación"** para que el jefe de taller confirme cantidades e ítems prefijados.
3. **Caso B (sin OTe):** Si la recepción no tiene orden externa, el coordinador abre la OTi "sin ítems" y la aprueba solo para evaluación técnica; la OTi queda en estado **"Aprobada para diagnóstico (pendiente de OTe)"** y habilita al jefe de taller para levantar los ítems desde cero.
4. **Notificación de habilitación:** Al aprobar, el sistema dispara una notificación (PUSH/WhatsApp) al jefe de taller: *"Vehículo [Placa/Sigla] habilitado para diagnóstico"*, indicando si es confirmación de cantidades de OTe o levantamiento de ítems.
5. **Entidad de facturación:** El coordinador puede ajustar la entidad y/o contrato de facturación de la OTi sin alterar la entidad propietaria original del vehículo.
6. **Carga de orden pendiente:** Si la recepción indica "con orden externa" pero no trae documento cargado, el sistema muestra el indicador "cargar orden" y permite cargar el documento antes de aprobar.
7. **Inmutabilidad:** Una recepción aprobada queda inmutable y no puede editarse ni volver a aprobarse.
8. **Trazabilidad:** Se registra log con fecha, hora y usuario que aprobó la recepción y creó la OTi.

### Criterios UX / Usabilidad

1. **Mínimo de clics (≤ 2 clics):** validar y aprobar desde el detalle de la recepción con un solo clic; la OTi se genera automáticamente sin pasos manuales.
2. **Autocompletado:** el encabezado de la OTi se precarga con los datos de la recepción (placa, entidad, kilometraje, fecha, corte).
3. **Confirmaciones en tiempo real:** al aprobar, el sistema confirma la creación de la OTi y el cambio de estado sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Aprobar la recepción y crear la OTi (caso feliz)**

Dado que el Coordinador validó la información de la recepción
Cuando pulsa "Aprobar" en el detalle de la recepción
Entonces el sistema crea automáticamente la OTi con el encabezado precargado y cambia la recepción a estado aprobado.

**Escenario 2: Aprobar con orden externa (caso feliz)**

Dado que la recepción tiene la orden externa cargada
Cuando el Coordinador revisa el PDF/foto y aprueba
Entonces la OTi queda en estado "Autorizada para diagnóstico y confirmación" y el jefe de taller queda habilitado para confirmar cantidades.

**Escenario 3: Aprobar sin orden externa (caso feliz)**

Dado que la recepción no tiene orden externa
Cuando el Coordinador aprueba
Entonces la OTi queda en estado "Aprobada para diagnóstico (pendiente de OTe)" y el jefe de taller queda habilitado para levantar los ítems desde cero.

**Escenario 4: Notificar la habilitación al jefe de taller (caso feliz)**

Dado que el Coordinador aprobó la recepción
Cuando la OTi cambia a estado habilitado
Entonces el sistema envía notificación PUSH/WhatsApp al jefe de taller indicando que el vehículo quedó habilitado para diagnóstico.

**Escenario 5: Ajustar la entidad de facturación sin alterar el propietario (caso feliz)**

Dado que un vehículo puede facturarse bajo otra entidad o contrato
Cuando el Coordinador selecciona la entidad de facturación en la OTi
Entonces el sistema conserva la entidad propietaria original y registra la entidad/contrato de facturación por separado.

**Escenario 6: Cargar la orden externa pendiente (excepción)**

Dado que la recepción indica "con orden externa" pero no trae el documento cargado
Cuando el Coordinador consulta la recepción
Entonces el sistema muestra el indicador "cargar orden" y permite cargar el documento antes de aprobar.

**Escenario 7: Bloqueo de aprobación sin validación (excepción)**

Dado que la recepción tiene información incompleta o inconsistente
Cuando el Coordinador intenta aprobarla
Entonces el sistema bloquea la aprobación y exige completar o validar los datos antes de continuar.

**Escenario 8: Inmutabilidad de la recepción aprobada (excepción)**

Dado que la recepción ya fue aprobada
Cuando se intenta editarla o aprobarla nuevamente
Entonces el sistema bloquea la edición y no permite una segunda aprobación.

**Escenario 9: Consecutivo único de la OTi (caso feliz)**

Dado que se aprueba una recepción
Cuando el sistema crea la OTi
Entonces asigna un consecutivo único global, sin numeraciones independientes por entidad.

**Escenario 10: Trazabilidad de la aprobación (caso feliz)**

Dado que el Coordinador aprobó la recepción
Cuando consulta el historial de la recepción
Entonces el sistema registra la fecha, hora y usuario que aprobó y creó la OTi.

### Matriz Delta de Cambios

**[ADDED]**
- Creación automática de la OTi con encabezado precargado y consecutivo único global.
- Estados de la OTi según el flujo: "Autorizada para diagnóstico y confirmación" (con OTe) y "Aprobada para diagnóstico (pendiente de OTe)" (sin OTe).
- Notificación PUSH/WhatsApp al jefe de taller al habilitar el diagnóstico.
- Ajuste de la entidad de facturación sin alterar la entidad propietaria original.
- Indicador "cargar orden" para la orden externa pendiente.
- Inmutabilidad y trazabilidad de la aprobación.

**[MODIFIED]**
- Aprobación: ahora desencadena la creación automática de la OTi (antes el encabezado se diligenciaba desde cero de manera manual).
- Flujo de órdenes clarificado: la OTi es obligatoria y la OTe no lo es.

**[REMOVED]**
- Diligenciamiento manual del encabezado de la orden de trabajo desde cero.
- Ambigüedad entre orden de trabajo interna y externa.
