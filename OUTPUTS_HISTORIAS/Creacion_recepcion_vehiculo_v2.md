# Creación de la recepción del vehículo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Creación de la recepción del vehículo |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Diligenciamiento de formatos e inventario por entidad |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Captura de firmas digitales en formularios |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Asesor de servicio (y Conductor / Coordinador administrativo en firmas) |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Crear recepciones de vehículos de manera asistida, diligenciar formatos e inventario por entidad y capturar firmas digitales, notificando a coordinación y taller |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta | x | Media |  |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Realizar la creación de recepciones de los vehículos, realizando un diligenciamiento inicial del documento de recepción, posteriormente que la nueva recepción sea notificada al área administrativa |  |  |  |

## Situación Actual

Actualmente el asesor de servicio diligencia un formato manual al momento de la recepción de un vehículo. El vehículo que llega debe tener amarrada una orden de trabajo enviada previamente por la entidad a la serviteca. Este documento de recepción contiene datos como: fecha de ingreso, hora de ingreso, consecutivo de orden de trabajo, nombre del propietario (Entidad), placa, marca, clase, modelo, color, kilometraje, descripción de la falla y observaciones del conductor. Dicha información es proporcionada principalmente por el conductor, quedando expuesta a errores de pronunciación o escritura por parte del asesor, lo que genera demoras en la recepción y poca trazabilidad de la información.

## Situación Deseada

Se desea que el proceso de creación de recepción de vehículos funcione de manera asistida a través de un formulario que permita crear nuevas recepciones y donde la mayoría de los datos requeridos sean consultados automáticamente desde la base de datos de vehículos y entidades. Esta mejora permitirá:
- Reducir errores de escritura y aumentar la velocidad de la recepción.
- Que el asesor se concentre en la descripción de la falla y las observaciones del conductor.
- Notificar oportunamente a coordinación y taller por múltiples canales (correo, WhatsApp y alertas en la aplicación).
- Aclarar el flujo de órdenes de trabajo: **la Orden de Trabajo externa (OTe) deja de ser obligatoria; la Orden de Trabajo interna (OTi) es la obligatoria** y se genera desde la coordinación.
- Registrar inventario, formatos por entidad y firmas digitales dentro del mismo flujo.

---

## HU_001 — Crear la recepción del vehículo

**Como** Asesor de servicio,
**Quiero** crear la recepción de un vehículo de manera asistida consultando estrictamente por placa o sigla,
**Para** agilizar el ingreso, eliminar errores de escritura y notificar oportunamente a coordinación y taller.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Asesor de servicio** y su firma digital configurada en el perfil.
2. La base de datos de vehículos y entidades debe estar previamente parametrizada (HU de gestión y carga de vehículos).
3. El formulario de recepción debe estar habilitado para el usuario autenticado.

### Especificación Técnica de Comportamiento

1. **Búsqueda estricta:** El sistema permite localizar vehículos estrictamente por **placa o sigla** (máscara en mayúsculas); no se admite búsqueda por entidad ni por contrato para evitar listas masivas.
2. **Autocompletado asíncrono:** Al confirmar la placa o sigla, el sistema consulta y autocompleta en **solo lectura**: Entidad, Marca, Clase, Modelo, Color y el último kilometraje registrado.
3. **Selector de flujo (Orden externa):** El formulario incluye un checkbox **"¿Ingresa con orden externa?"**.
   - Si se marca **SÍ**: se despliega un campo para cargar el documento de la orden (archivo, foto o cámara). Si el asesor no tiene el documento a la mano, puede guardar y notificar a coordinación, que cargará la orden posteriormente.
   - Si se marca **NO**: no se despliega campo de carga; el sistema permite guardar la recepción con la alerta *"Recepción creada - Sin OT vinculada"* y notifica a coordinación para gestionar la OTi.
4. **Validación de kilometraje en tiempo real (Requerido):** El kilometraje debe ser un número entero estrictamente mayor o igual al último registro histórico. Si es menor, negativo o decimal, se muestra una alerta emergente con el último kilometraje registrado.
5. **Vehículo no registrado:** Si la placa o sigla no existe en la base de datos, el sistema permite registrar los datos básicos disponibles, muestra la alerta *"Vehículo no registrado. Solicite la carga a Administración"*, notifica a coordinación y deja el vehículo inhabilitado para operación para operación hasta su validación.
6. **Notificaciones multicanal:** Al guardar la recepción, se notifica simultáneamente al coordinador administrativo y al jefe de taller por correo (con el PDF de la recepción adjunto), WhatsApp y alerta visual en la campanita del panel.
7. **Inmutabilidad:** Una recepción aprobada por coordinación queda inmutable y no puede editarse ni volver a aprobarse.

### Criterios UX / Usabilidad

1. **Mínimo de clics (≤ 3 clics):** digitar placa/sigla y confirmar → autocompleta los datos; cargar evidencia (si aplica) → guardar. El flujo principal no supera tres clics.
2. **Autocompletado y precarga:** Entidad, Marca, Clase, Modelo, Color y último kilometraje se precargan en solo lectura.
3. **Confirmaciones en tiempo real:** la búsqueda del vehículo y la validación del kilometraje se ejecutan de forma asíncrona, sin recargar la pantalla.
4. **Firma interna automática:** la firma del asesor se toma del perfil autenticado, sin botón de firma manual.

### Criterios de Aceptación

**Escenario 1: Autocompletar los datos del vehículo por placa o sigla (caso feliz)**

Dado que el Asesor de servicio digita una placa o sigla existente en la base de datos
Cuando confirma la búsqueda
Entonces el sistema autocompleta en solo lectura la Entidad, Marca, Clase, Modelo, Color y el último kilometraje registrado.

**Escenario 2: Guardar la recepción con orden externa (caso feliz)**

Dado que el Asesor marcó el checkbox "Ingresa con orden externa"
Cuando carga el documento de la orden y guarda la recepción
Entonces el sistema registra la recepción vinculada a la orden y notifica a coordinación y taller.

**Escenario 3: Guardar la recepción sin orden externa (flujo no bloqueante)**

Dado que el Asesor no marcó el checkbox de orden externa
Cuando guarda la recepción
Entonces el sistema permite guardar con la alerta "Recepción creada - Sin OT vinculada" y notifica a coordinación para gestionar la Orden de Trabajo interna.

**Escenario 4: Validar kilometraje menor al último registrado (excepción)**

Dado que el Asesor ingresa un kilometraje menor al último registrado históricamente
Cuando avanza al siguiente campo
Entonces el sistema muestra una alerta emergente indicando el último kilometraje registrado.

**Escenario 5: Validar kilometraje inválido (excepción)**

Dado que el Asesor ingresa un kilometraje negativo o con decimales
Cuando avanza al siguiente campo
Entonces el sistema muestra la alerta "Kilometraje no válido" y no permite continuar.

**Escenario 6: Vehículo no registrado (excepción)**

Dado que el Asesor digita una placa o sigla que no existe en la base de datos
Cuando confirma la búsqueda
Entonces el sistema permite registrar los datos básicos disponibles, muestra la alerta "Vehículo no registrado. Solicite la carga a Administración", notifica a coordinación y bloquea el vehículo para operación hasta su validación.

**Escenario 7: Notificar a coordinación por múltiples canales (caso feliz)**

Dado que se guardó una nueva recepción
Cuando el sistema confirma el guardado
Entonces notifica al coordinador administrativo por correo con el PDF adjunto, WhatsApp y alerta visual en la campanita del panel.

**Escenario 8: Notificar al jefe de taller con restricciones (caso feliz)**

Dado que se guardó una nueva recepción
Cuando el jefe de taller visualiza el vehículo en su dashboard
Entonces lo ve en solo lectura, con el botón "Iniciar Diagnóstico" habilitado y el botón "Iniciar Reparación" deshabilitado con la etiqueta "Requiere Aprobación Administrativa".

**Escenario 9: Recepción con orden externa pero sin documento a la mano (excepción)**

Dado que el Asesor marcó "Ingresa con orden externa" pero no dispone del documento en ese momento
Cuando guarda la recepción sin cargar la orden
Entonces el sistema notifica a coordinación con el indicador "cargar orden" para que la administración cargue el documento posteriormente.

**Escenario 10: Inmutabilidad de la recepción aprobada (excepción)**

Dado que una recepción fue aprobada por el coordinador administrativo
Cuando se intenta editar su contenido
Entonces el sistema bloquea la edición y la recepción queda inmutable.

### Matriz Delta de Cambios

**[ADDED]**
- Checkbox "Ingresa con orden externa" con carga de evidencia (archivo, foto o cámara).
- Autocompletado del último kilometraje registrado como dato de solo lectura.
- Notificaciones multicanal (correo con PDF, WhatsApp y alerta visual en campanita).
- Inmutabilidad de la recepción aprobada.
- Flujo de vehículo no registrado con registro de datos disponibles y bloqueo hasta validación de coordinación.

**[MODIFIED]**
- Búsqueda: estrictamente por placa o sigla, eliminando entidad y contrato como filtro principal.
- Integración de las consultas de entidad y de vehículo (HU_002 y HU_003 originales) como componente de autocompletado dentro de HU_001.
- Validación de kilometraje: ahora con alerta emergente (popup) bloqueante y mensaje del último valor registrado.
- Firma del asesor: se toma automáticamente del perfil autenticado.

**[REMOVED]**
- Regla de negocio que exigía orden de trabajo enviada con antelación por la entidad (la OTe deja de ser obligatoria).
- Búsqueda por entidad o por contrato.
- Botón de firma manual para el personal interno.

---

## HU_002 — Diligenciar los formatos e inventario por entidad

**Como** Asesor de servicio,
**Quiero** diligenciar los formatos y el inventario específicos de cada entidad,
**Para** cumplir los requisitos documentales de la entidad y certificar el estado físico del vehículo al ingreso y a la salida.

### Precondiciones

1. El usuario debe tener una sesión activa con el rol de **Asesor de servicio**.
2. El vehículo debe pertenecer a una entidad con contrato vigente parametrizada previamente en el sistema.
3. Debe existir un formulario de recepción y/o entrega en ejecución.

### Especificación Técnica de Comportamiento

1. **Despliegue dinámico:** Al identificar la entidad (por autocompletado de la placa/sigla), el sistema despliega automáticamente el formato de ingreso y el inventario configurado para los requisitos de esa entidad.
2. **Formato adicional por entidad:** Si la entidad exige un formato de ingreso adicional al del taller, el sistema lo muestra como una ventana adicional y es **bloqueante**: no permite confirmar que el vehículo fue ingresado hasta diligenciarlo.
3. **Lista de chequeo:** Se visualiza una lista de chequeo de inventario mediante checkboxes (Kit de carretera, llanta de repuesto, extintor, copas, etc.) correspondiente a los requerimientos de la institución.
4. **Mapeo de carrocería:** Se incluye un esquema 2D interactivo del vehículo que permite marcar con un tap la ubicación exacta de rayones o golpes y añadir comentarios.
5. **Condicionalidad del inventario:** El registro del inventario es obligatorio **sí y solo sí** la entidad lo exige en su configuración; nunca es opcional para quien lo requiere (ej. Seguridad y Justicia lo exige, CBC no).
6. **Restricción de salida:** El formulario de salida se habilita únicamente cuando la recepción cuenta con la aprobación previa del coordinador administrativo.

### Criterios UX / Usabilidad

1. **Despliegue automático:** el formato e inventario aparecen automáticamente al identificar la entidad, sin clics adicionales.
2. **Checkboxes precargados:** la lista de chequeo se muestra lista para marcar, según la configuración de la entidad.
3. **Confirmación en tiempo real:** al marcar daños en el esquema 2D, el registro se guarda en el momento sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Desplegar el formato e inventario de la entidad (caso feliz)**

Dado que el Asesor digitó la placa de un vehículo cuya entidad tiene formato e inventario configurados
Cuando el sistema identifica la entidad
Entonces despliega automáticamente el formato de ingreso y la lista de chequeo de inventario de esa entidad.

**Escenario 2: Formato adicional bloqueante (excepción)**

Dado que la entidad exige un formato de ingreso adicional
Cuando el Asesor intenta confirmar el ingreso sin diligenciarlo
Entonces el sistema bloquea la confirmación y muestra la ventana de "formato adicional" hasta que se diligencie.

**Escenario 3: Registrar el inventario obligatorio de la entidad (caso feliz)**

Dado que la entidad exige el inventario en su configuración
Cuando el Asesor marca los checkboxes de la lista de chequeo
Entonces el sistema permite guardar el inventario como parte del formulario de ingreso.

**Escenario 4: Inventario no exigido por la entidad (excepción)**

Dado que la entidad no exige inventario en su configuración
Cuando el Asesor registra el ingreso del vehículo
Entonces el sistema no obliga a diligenciar la lista de inventario.

**Escenario 5: Mapear daños en la carrocería (caso feliz)**

Dado que el Asesor está diligenciando el formulario de ingreso
Cuando marca con un tap la ubicación de un rayón o golpe en el esquema 2D
Entonces el sistema registra la marca con su comentario y la guarda en la recepción.

**Escenario 6: Restricción de salida sin aprobación (excepción)**

Dado que la recepción no cuenta con la aprobación del coordinador administrativo
Cuando se intenta habilitar el formulario de salida
Entonces el sistema no permite diligenciar la salida.

**Escenario 7: Restricción de rol sobre el diseño del formato (excepción)**

Dado que el Asesor consume y diligencia el formato e inventario asignado a la entidad
Cuando intenta modificar el diseño del formato
Entonces el sistema no lo permite, porque solo la administración puede configurar formatos.

### Matriz Delta de Cambios

**[ADDED]**
- Formato de ingreso adicional por entidad, bloqueante hasta su diligenciamiento.
- Mapeo de carrocería 2D interactivo con marcado de daños y comentarios.
- Condicionalidad estricta del inventario (obligatorio sí y solo sí la entidad lo exige).

**[MODIFIED]**
- Unificación de la configuración de formatos y del registro de inventario en una sola historia (antes HU_006 y HU_007 por separado).
- Despliegue del formato e inventario automático al identificar la entidad desde la placa/sigla.

**[REMOVED]**
- La palabra "opcional" aplicada al inventario: el inventario nunca es opcional para la entidad que lo exige.

---

## HU_003 — Capturar las firmas digitales en los formularios

**Como** Conductor, Asesor de servicio y Coordinador administrativo,
**Quiero** plasmar las firmas digitales en los formularios de recepción y entrega,
**Para** dar validez legal y de conformidad a los documentos de ingreso y salida del vehículo.

### Precondiciones

1. El personal interno debe estar autenticado y contar con su firma digital configurada en el perfil.
2. El usuario debe encontrarse en la etapa final de diligenciamiento de un formulario de ingreso o salida.
3. Debe existir un dispositivo con pantalla táctil o lienzo de captura para la firma del conductor.

### Especificación Técnica de Comportamiento

1. **Lienzo de captura:** El sistema habilita un espacio interactivo de pantalla táctil para la captura de la firma dibujada manualmente por el conductor o responsable de la entrega.
2. **Ingreso (doble firma):** Se exigen obligatoriamente dos firmas: (1) responsable de la entrega (Conductor) y (2) responsable de la recepción (Asesor).
3. **Salida (firma única):** Se exige obligatoriamente una firma: la del responsable de la entrega (Conductor).
4. **Firma interna automática:** La firma del asesor se toma automáticamente del perfil del usuario autenticado; se elimina el botón de firma manual para el personal interno.
5. **Firma no configurada:** Si el usuario interno no tiene firma configurada, el sistema le permite registrarla directamente en el formulario y la guarda en su perfil para los próximos procesos (no bloqueante).

### Criterios UX / Usabilidad

1. **Firma interna automática:** el asesor no requiere acción manual; su firma se aplica desde el perfil.
2. **Un solo lienzo para el conductor:** la firma del responsable se captura en un único espacio en pantalla.
3. **Confirmación en tiempo real:** la firma capturada se muestra inmediatamente en el formulario sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Firma obligatoria del conductor en el ingreso (caso feliz)**

Dado que el formulario de recepción está en su etapa final de diligenciamiento
Cuando el conductor firma en el lienzo habilitado
Entonces el sistema registra la firma y permite guardar la recepción.

**Escenario 2: Doble firma en el ingreso (caso feliz)**

Dado que el conductor firmó la recepción
Y el asesor tiene su firma configurada en el perfil
Cuando se guarda la recepción
Entonces el sistema registra automáticamente la firma del asesor junto con la del conductor.

**Escenario 3: Bloqueo sin la firma del conductor (excepción)**

Dado que el conductor no ha firmado en el lienzo
Cuando se intenta guardar la recepción
Entonces el sistema bloquea el guardado y exige la firma manuscrita del conductor.

**Escenario 4: Firma del asesor aplicada automáticamente (caso feliz)**

Dado que el asesor está autenticado con su firma configurada
Cuando guarda el formulario
Entonces el sistema aplica su firma automáticamente desde el perfil, sin requerir un botón de firma.

**Escenario 5: Firma interna no configurada (excepción)**

Dado que el asesor no tiene una firma configurada en su perfil
Cuando guarda el formulario
Entonces el sistema le permite registrar la firma en ese momento y la guarda en su perfil para los próximos procesos.

**Escenario 6: Firma única de salida del conductor (caso feliz)**

Dado que el vehículo está listo para la entrega
Cuando el conductor firma en el formulario de salida
Entonces el sistema registra la firma y permite finalizar la entrega.

### Matriz Delta de Cambios

**[ADDED]**
- Aplicación automática de la firma del asesor desde el perfil del usuario autenticado.
- Registro en caliente de la firma interna cuando no está configurada, con guardado automático en el perfil.
- Distinción explícita entre ingreso (doble firma) y salida (firma única).

**[MODIFIED]**
- Captura de firma del conductor mediante lienzo interactivo en pantalla táctil.
- Redacción de la narrativa en formato INVEST con múltiples roles (Conductor, Asesor y Coordinador).

**[REMOVED]**
- Botón de firma manual para el personal interno (reemplazado por la firma automática del perfil).
