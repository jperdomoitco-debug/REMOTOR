# Creación de la recepción del vehículo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Creación de la Recepción del Vehículo |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Diligenciamiento de Formatos e Inventario por Entidad |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Firmas Digitales en Formularios |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Asesor de servicio |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Crear la recepción del vehículo de forma asistida, diligenciar los formatos e inventario de la entidad y capturar las firmas; al guardar, el sistema genera automáticamente la Orden de Trabajo interna (OTi) y notifica a coordinación |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta | x | Media |  |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Creación ágil de recepciones, autocompletado por placa o sigla, carga de evidencia de la orden externa y notificación al área administrativa. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Generación automática de la OTi al crear la recepción (con OTe, sin OTe y excepción de garantía), consecutivo global de la recepción, inmutabilidad del registro y notificación a coordinación a través del módulo transversal. |  |  |  |

## Situación Actual

Actualmente el asesor de servicio diligencia un formato manual al momento de la recepción de un vehículo. Este documento contiene datos como fecha y hora de ingreso, consecutivo, entidad, placa, marca, clase, modelo, color, kilometraje, descripción de la falla y observaciones del conductor. Dicha información es proporcionada principalmente por el conductor, lo que expone el proceso a errores de pronunciación o escritura, demoras en la recepción y poca trazabilidad de la información.

## Situación Deseada

Se desea que el proceso de creación de la recepción funcione de manera asistida mediante un formulario donde la mayoría de los datos se consulten directamente contra las entidades y los vehículos registrados. Al guardar la recepción, el sistema genera automáticamente la Orden de Trabajo interna (OTi) y notifica a coordinación, quien instruye al jefe de taller sobre el diagnóstico o la orden a ejecutar. Esta mejora reduce errores de escritura, acelera el ingreso y elimina la dependencia de la aprobación administrativa de la recepción.

---

## HU_001 — Creación de la Recepción del Vehículo

**Como** Asesor de servicio,
**Quiero** crear la recepción de un vehículo de forma asistida, consultando estrictamente por placa o sigla y con autocompletado en solo lectura,
**Para** registrar el ingreso, generar automáticamente la Orden de Trabajo interna y notificar a coordinación de forma oportuna.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Asesor de servicio** y su firma digital configurada.
**2.** La base de datos de vehículos y entidades debe estar previamente parametrizada.
**3.** El vehículo debe estar registrado en el sistema; si no lo está, se registran los datos disponibles para su validación posterior por coordinación.

### Especificación Técnica de Comportamiento

**1.** **Búsqueda estricta:** El sistema permite buscar vehículos únicamente por **placa o sigla**. No se admite la búsqueda por entidad ni por contrato para evitar listas masivas.

**2.** **Autocompletado en solo lectura:** Al ingresar la placa o sigla, el sistema autocompleta en modo de solo lectura los campos Entidad, Marca, Clase, Modelo, Color y último kilometraje.

**3.** **Selector de flujo:** El formulario incluye un checkbox "Ingresa con orden externa" y un indicador específico para ingresos por **garantía**.

**4.** **Consecutivo global de la recepción:** Cada recepción recibe un consecutivo global único y continuo, independiente del consecutivo de la OTi.

**5.** **Generación automática de la OTi:** Al guardar la recepción, el sistema genera automáticamente la OTi:
   - **Con orden externa:** la OTi se crea en estado "Autorizada para diagnóstico y confirmación".
   - **Sin orden externa:** la OTi se crea con los ítems vacíos para el diagnóstico del jefe de taller.
   - **Garantía:** no se genera la OTi automática; el ingreso se registra con el indicador de garantía.

**6.** **Inmutabilidad:** Una recepción creada no puede eliminarse del sistema, garantizando la trazabilidad documental.

**7.** **Notificación:** Al guardar la recepción, el módulo transversal de notificaciones alerta a coordinación (correo, WhatsApp y campanita).

**8.** **Vehículo no registrado:** Si la placa o sigla no existe, el asesor registra los datos básicos disponibles, el sistema notifica a coordinación y el vehículo queda pendiente de validación administrativa.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** digitar placa o sigla → autocompleta los datos → indicar el flujo → guardar. El flujo principal no supera tres clics.
**2.** **Autocompletado y precarga:** Entidad, Marca, Clase, Modelo, Color y último kilometraje se precargan en solo lectura.
**3.** **Confirmaciones en tiempo real:** la búsqueda del vehículo y la validación del kilometraje se ejecutan de forma asíncrona, sin recargar la pantalla.
**4.** **Firma interna automática:** la firma del asesor se toma del perfil autenticado, sin botón de firma manual.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Crear la recepción con autocompletado (caso feliz)**

**Dado que** el Asesor de servicio digita una placa o sigla válida
**Cuando** confirma la búsqueda
**Entonces** el sistema autocompleta en solo lectura la Entidad, Marca, Clase, Modelo, Color y el último kilometraje.

**Escenario 2: Generar automáticamente la OTi con orden externa (caso feliz)**

**Dado que** el vehículo ingresa con orden externa
**Cuando** el Asesor guarda la recepción
**Entonces** el sistema crea automáticamente la OTi asociada en estado "Autorizada para diagnóstico y confirmación".

**Escenario 3: Generar automáticamente la OTi sin orden externa (caso feliz)**

**Dado que** el vehículo ingresa sin orden externa
**Cuando** el Asesor guarda la recepción
**Entonces** el sistema crea automáticamente la OTi con los ítems vacíos para el diagnóstico del jefe de taller.

**Escenario 4: Ingreso por garantía sin OTi automática (excepción)**

**Dado que** el ingreso del vehículo corresponde a una garantía
**Cuando** el Asesor guarda la recepción con el indicador de garantía
**Entonces** el sistema no genera la OTi automática y registra el ingreso mediante dicho indicador.

**Escenario 5: Asignar el consecutivo global de la recepción (caso feliz)**

**Dado que** se guarda una nueva recepción
**Cuando** el sistema la registra
**Entonces** asigna un consecutivo global único, independiente del consecutivo de la OTi.

**Escenario 6: Validar el kilometraje (excepción)**

**Dado que** el kilometraje ingresado es menor al último registro del vehículo
**Cuando** el Asesor avanza al siguiente campo
**Entonces** el sistema emite una alerta en tiempo real y exige corregir el valor antes de guardar.

**Escenario 7: Vehículo no registrado (excepción)**

**Dado que** la placa o sigla digitada no existe en la base de datos
**Cuando** el Asesor registra la recepción con los datos disponibles
**Entonces** el sistema notifica a coordinación y deja el vehículo pendiente de validación administrativa.

**Escenario 8: Inmutabilidad de la recepción (excepción)**

**Dado que** una recepción ya fue creada
**Cuando** se intenta eliminarla del sistema
**Entonces** el sistema no permite su eliminación para conservar la trazabilidad.

**Escenario 9: Notificar a coordinación (caso feliz)**

**Dado que** el Asesor guardó una nueva recepción
**Cuando** el sistema confirma el guardado
**Entonces** el módulo transversal notifica a coordinación por correo, WhatsApp y campanita.

### Matriz Delta de Cambios

**[ADDED]**
- Generación automática de la OTi al guardar la recepción (con OTe, sin OTe con ítems vacíos y excepción por garantía).
- Consecutivo global único de la recepción, independiente del consecutivo de la OTi.
- Indicador específico de garantía como única excepción a la generación automática de la OTi.
- Inmutabilidad total de la recepción (no eliminable).
- Referencia al módulo transversal de notificaciones para comunicar a coordinación.

**[MODIFIED]**
- Notificación: ahora se dirige a coordinación, quien instruye al jefe de taller sobre el diagnóstico o la orden a ejecutar (antes se notificaba en paralelo a coordinación y taller).
- Validación de kilometraje: expresada como regla de negocio concisa (valor entero, mayor o igual al último registro), sin escenarios de prueba detallados.
- Nomenclatura estandarizada OTe / OTi en todo el flujo.

**[REMOVED]**
- Toda referencia a la "aprobación" de la recepción (el ingreso es independiente de la validación administrativa).
- Creación posterior o manual de la OTi desde el área administrativa como paso requerido.

---

## HU_002 — Diligenciamiento de Formatos e Inventario por Entidad

**Como** Asesor de servicio,
**Quiero** diligenciar los inventarios y formatos específicos de cada entidad,
**Para** asegurar que se visualicen los campos requeridos según el contrato y realizar una inspección básica al momento del ingreso o salida.

### Precondiciones

**1.** Usuario autenticado con rol **Asesor de servicio**.
**2.** El vehículo debe pertenecer a una entidad con contrato parametrizada previamente en el sistema.
**3.** Formulario de recepción y/o entrega en ejecución.

### Especificación Técnica de Comportamiento

**1.** **Despliegue dinámico:** Al identificar la entidad, el sistema despliega automáticamente el formato de ingreso y el inventario configurado específicamente para esa entidad.
**2.** **Controles de chequeo:** Se visualiza una lista de chequeo de inventario (mediante checkboxes) correspondiente a los requerimientos documentales asignados a la entidad.
**3.** **Mapeo de carrocería:** Se dispone de un esquema 2D interactivo del vehículo que permite marcar daños visibles y añadir comentarios.
**4.** **Condicionalidad del inventario:** El inventario es obligatorio sí y solo sí la entidad lo exige en su configuración.

### Criterios UX / Usabilidad

**1.** **Despliegue automático:** el formato e inventario aparecen automáticamente al identificar la entidad, sin clics adicionales.
**2.** **Checkboxes precargados:** la lista de chequeo se muestra lista para marcar, según la configuración de la entidad.
**3.** **Confirmación en tiempo real:** al marcar daños en el esquema 2D, el registro se guarda en el momento sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Desplegar el formato e inventario al identificar la entidad (caso feliz)**

**Dado que** el Asesor identifica la entidad del vehículo desde la placa o sigla
**Cuando** el sistema reconoce la entidad
**Entonces** despliega automáticamente el formato de ingreso y el inventario configurados para esa entidad.

**Escenario 2: Inventario condicional según la entidad (excepción)**

**Dado que** la entidad no exige inventario en su configuración
**Cuando** el Asesor diligencia el formato de ingreso
**Entonces** el sistema no exige la lista de chequeo; si la entidad sí lo exige, el inventario es obligatorio para guardar.

**Escenario 3: Marcar daños en el esquema 2D (caso feliz)**

**Dado que** el formulario de ingreso está en ejecución
**Cuando** el Asesor marca un daño sobre el esquema 2D del vehículo
**Entonces** el sistema guarda el marcado y su comentario en tiempo real.

**Escenario 4: Asesor sin permisos de configuración (excepción)**

**Dado que** el Asesor de servicio intenta alterar el diseño de un formato o inventario
**Cuando** intenta editarlo
**Entonces** el sistema bloquea la edición porque la configuración corresponde al área administrativa.

**Escenario 5: Habilitar el formulario de salida (excepción)**

**Dado que** el vehículo finalizó el servicio y se inicia la entrega
**Cuando** el Asesor abre el formulario de salida
**Entonces** el sistema habilita el formato de salida de la entidad con los datos del vehículo precargados.

### Matriz Delta de Cambios

**[ADDED]**
- Esquema 2D interactivo de carrocería con marcado de daños y comentarios en tiempo real.
- Condicionalidad estricta del inventario (obligatorio sí y solo sí la entidad lo exige).

**[MODIFIED]**
- Habilitación del formulario de salida: ya no depende de una "aprobación" de la recepción, sino del inicio de la entrega una vez finalizado el servicio.
- Criterios de aceptación reescritos en Gherkin conciso a nivel de negocio.

**[REMOVED]**
- La palabra "opcional" aplicada al inventario: el inventario nunca es opcional para la entidad que lo exige.
- Referencias a la aprobación previa del coordinador como condición para diligenciar la salida.

---

## HU_003 — Firmas Digitales en Formularios

**Como** Asesor de servicio,
**Quiero** habilitar el espacio de captura de firmas en los formularios de recepción y entrega,
**Para** formalizar el proceso, asegurar la validez legal del servicio y garantizar la conformidad de las partes.

### Precondiciones

**1.** Usuario autenticado con rol **Asesor de servicio**.
**2.** El usuario se encuentra en la etapa final de diligenciamiento de cualquier formulario de ingreso o salida.
**3.** El asesor de servicio cuenta con una firma configurada en su perfil activo.

### Especificación Técnica de Comportamiento

**1.** **Lienzo de captura:** El sistema habilita un espacio interactivo de pantalla táctil para la captura de la firma dibujada manualmente por el conductor o responsable de la entrega del vehículo.
**2.** **Firma interna automática:** La firma del asesor se aplica automáticamente desde el perfil del usuario autenticado.
**3.** **Distinción de formularios:** El ingreso exige doble firma (conductor y asesor); la salida exige la firma única del responsable de la entrega.

### Criterios UX / Usabilidad

**1.** **Firma interna automática:** el asesor no requiere acción manual; su firma se aplica desde el perfil.
**2.** **Un solo lienzo para el conductor:** la firma del responsable se captura en un único espacio en pantalla.
**3.** **Confirmación en tiempo real:** la firma capturada se muestra inmediatamente en el formulario sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Firma obligatoria del conductor (excepción)**

**Dado que** el formulario de ingreso está listo para guardar
**Cuando** no se ha capturado la firma del conductor o responsable
**Entonces** el sistema no permite guardar y exige la firma manuscrita en pantalla.

**Escenario 2: Aplicar la firma del asesor automáticamente (caso feliz)**

**Dado que** el Asesor de servicio está autenticado con firma configurada
**Cuando** guarda el formulario
**Entonces** el sistema aplica su firma automáticamente desde el perfil, sin captura manual.

**Escenario 3: Registrar la firma interna no configurada (caso feliz)**

**Dado que** el usuario activo no tiene una firma digital configurada
**Cuando** firma dentro del formulario
**Entonces** el sistema la guarda en su perfil y la reutiliza en próximos procesos.

**Escenario 4: Distinguir ingreso y salida (caso feliz)**

**Dado que** se diligencia un formulario de ingreso o de salida
**Cuando** el sistema solicita las firmas
**Entonces** exige doble firma en el ingreso y firma única del responsable en la salida.

### Matriz Delta de Cambios

**[ADDED]**
- Distinción explícita entre ingreso (doble firma) y salida (firma única).

**[MODIFIED]**
- Criterios de aceptación reescritos en Gherkin conciso a nivel de negocio.
- Redacción de la narrativa en formato INVEST con múltiples roles (Conductor y Asesor).

**[REMOVED]**
- Botón de firma manual para el personal interno (reemplazado por la firma automática del perfil).
