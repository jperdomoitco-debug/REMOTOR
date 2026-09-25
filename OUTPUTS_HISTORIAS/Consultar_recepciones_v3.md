# Consultar recepciones

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar las recepciones de vehículos |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo y Jefe de taller |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Consultar las recepciones de vehículos desde un formulario maestro para revisar la información y completar las validaciones de datos |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Consultar y aprobar recepciones mediante búsqueda por placa o sigla y generar automáticamente la OTi con el encabezado precargado. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Consulta de recepciones ampliada al jefe de taller, eliminación de la aprobación de recepciones y búsqueda estricta por placa o sigla. |  |  |  |

## Situación Actual

Actualmente las recepciones deben ser comunicadas de manera presencial al coordinador administrativo: el asesor de servicio debe desplazarse hasta el área administrativa para entregar el documento diligenciado a mano. Esto hace que la continuidad del proceso dependa de que el asesor llegue de manera oportuna a entregar la recepción.

## Situación Deseada

Se desea que el coordinador administrativo y el jefe de taller puedan consultar las recepciones de los vehículos desde un formulario maestro, revisar la información y realizar las validaciones de datos correspondientes. El ingreso del vehículo ocurre de manera independiente de la validación administrativa: la Orden de Trabajo interna (OTi) se genera automáticamente al crear la recepción, por lo que la consulta ya no incluye un flujo de aprobación.

---

## HU_001 — Consultar las recepciones de vehículos

**Como** Coordinador administrativo y Jefe de taller,
**Quiero** consultar las recepciones de vehículos desde un formulario maestro,
**Para** revisar la información y completar las validaciones de datos sin depender de la entrega presencial de documentos físicos.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo** o **Jefe de taller**.
**2.** Deben existir recepciones registradas por el **Asesor de servicio** en el sistema.
**3.** La base de datos de vehículos y entidades debe estar parametrizada.

### Especificación Técnica de Comportamiento

**1.** **Listado de recepciones:** El sistema muestra una tabla de recepciones con placa/sigla, entidad, fecha y hora de ingreso, kilometraje y estado.
**2.** **Búsqueda estricta:** La búsqueda se realiza estrictamente por placa o sigla; no se admite búsqueda por entidad ni por contrato para evitar listas masivas.
**3.** **Detalle en solo lectura:** Al seleccionar una recepción, el sistema despliega el detalle completo: entidad, marca, clase, modelo, color, kilometraje, descripción de la falla, observaciones, inventario, daños de carrocería y la evidencia de la orden externa si aplica.
**4.** **Contratos informativos:** El contrato asociado se muestra como dato de solo lectura, sin usarse como filtro de búsqueda.
**5.** **Resaltado de recepciones sin orden:** Las recepciones creadas sin orden externa se resaltan con la etiqueta "Sin OT vinculada".
**6.** **Vehículo no registrado:** Las recepciones de vehículos no registrados se muestran con la alerta "Pendiente de validación administrativa" para que coordinación complete y guarde los datos del vehículo.
**7.** **Acceso desde la notificación:** El coordinador puede abrir el detalle de una recepción directamente desde la alerta recibida en la campanita o el correo.
**8.** **Ampliación de roles:** La consulta está habilitada tanto para el coordinador administrativo como para el jefe de taller.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** un clic abre el detalle desde el listado o desde la notificación, sin salir del formulario maestro.
**2.** **Autocompletado y precarga:** el listado y el detalle se precargan con los datos capturados en la recepción, en modo solo lectura.
**3.** **Confirmaciones en tiempo real:** la búsqueda por placa/sigla y los filtros se ejecutan de forma asíncrona, sin recargar la pantalla.
**4.** **Filtros en línea:** permite filtrar por estado, fecha y placa sin recargar.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Visualizar el listado de recepciones (caso feliz)**

**Dado que** el usuario está autenticado con un rol habilitado
Y existen recepciones registradas en el sistema
**Cuando** abre el formulario maestro de recepciones
**Entonces** el sistema muestra la tabla de recepciones con placa, entidad, fecha, hora, kilometraje y estado.

**Escenario 2: Buscar una recepción por placa o sigla (caso feliz)**

**Dado que** el usuario desea localizar una recepción
**Cuando** digita la placa o sigla del vehículo y confirma la búsqueda
**Entonces** el sistema filtra y muestra únicamente la recepción correspondiente a esa placa o sigla.

**Escenario 3: Bloquear la búsqueda por entidad o contrato (excepción)**

**Dado que** el usuario intenta buscar recepciones por entidad o contrato
**Cuando** ejecuta la búsqueda
**Entonces** el sistema no lo permite y exige la búsqueda por placa o sigla.

**Escenario 4: Visualizar el detalle de una recepción (caso feliz)**

**Dado que** el listado de recepciones está visible
**Cuando** el usuario selecciona una recepción
**Entonces** el sistema muestra el detalle completo en solo lectura: entidad, marca, clase, modelo, color, kilometraje, falla, observaciones, inventario, daños y evidencia de la orden si aplica.

**Escenario 5: Identificar una recepción sin orden externa (caso feliz)**

**Dado que** existe una recepción creada sin orden externa
**Cuando** el usuario consulta el listado
**Entonces** el sistema resalta la recepción con la etiqueta "Sin OT vinculada".

**Escenario 6: Vehículo no registrado pendiente de validación (excepción)**

**Dado que** una recepción corresponde a un vehículo no registrado
**Cuando** el usuario abre su detalle
**Entonces** el sistema muestra los datos parciales ingresados por recepción y la alerta "Pendiente de validación administrativa" para completar y guardar el vehículo.

**Escenario 7: Notificar la nueva recepción al coordinador (caso feliz)**

**Dado que** el Asesor de servicio guarda una nueva recepción
**Cuando** el sistema confirma el guardado
**Entonces** el módulo transversal notifica al coordinador en la campanita y por correo, con acceso directo al detalle de la recepción.

**Escenario 8: Consultar como jefe de taller (caso feliz)**

**Dado que** el Jefe de taller está autenticado con el rol habilitado
**Cuando** abre el formulario maestro de recepciones
**Entonces** el sistema le permite consultar las recepciones de los vehículos ingresados.

**Escenario 9: Filtrar recepciones por estado (caso feliz)**

**Dado que** el listado de recepciones está visible
**Cuando** el usuario selecciona un estado en el filtro
**Entonces** el sistema muestra únicamente las recepciones con ese estado, sin recargar la pantalla.

### Matriz Delta de Cambios

**[ADDED]**
- Ampliación de roles: la consulta de recepciones queda habilitada también para el Jefe de taller.
- Bloqueo explícito de la búsqueda por entidad o contrato.
- Referencia al módulo transversal para la notificación al coordinador.

**[MODIFIED]**
- Eliminación del flujo de aprobación: la consulta ya no incluye el paso de aprobar la recepción.
- Criterios de aceptación consolidados a nivel de negocio, en Gherkin conciso.

**[REMOVED]**
- HU_002 "Aprobar la recepción y crear la Orden de Trabajo interna": la OTi se genera automáticamente al crear la recepción, sin aprobación previa.
- Búsqueda de recepciones por entidad o por contrato.
