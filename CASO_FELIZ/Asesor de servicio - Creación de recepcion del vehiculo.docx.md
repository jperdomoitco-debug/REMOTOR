# Creación de la recepción del vehículo

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Creación de la Recepción del Vehículo |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Diligenciamiento de Formatos e Inventario por Entidad |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Firmas Digitales en Formularios |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Asesor de servicio |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | ealizar la creación de recepciones de los vehículos, realizando un diligenciamiento inicial del documento de recepción, posteriormente que la nueva recepción sea notificada al área administrativa  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta | x | Media |  |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Se requiere la creación ágil de recepciones y notificación de creación de estas al área administrativa |  |  |  |

## Situación Actual

Actualmente el asesor de servicio diligencia un formato de manual al momento de la recepción de un vehículo, (el vehículo que llega debe tener amarrada una orden de trabajo que ya ha enviado la entidad a la serviteca), este documento de recepción contiene datos como:  Fecha de ingreso Hora de ingreso Consecutivo de orden de trabajo Nombre del propietario (Entidad) Placa Marca Clase Modelo Color Kilometraje Descripción de la falla Observaciones del conductor Dicha información debe ser proporcionada principalmente por el conductor quedando expuesto a errores de pronunciación o escritura por parte del asesor de servicio. Además de lograr demoras en la recepción y poca trazabilidad de la información relacionada a las recepciones.

## Situación Deseada

Se desea que el proceso de creación de recepción de vehículos funcione de manera asistida a través de un formulario que permita crear nuevas recepciones y donde la mayoría de los datos requeridos sean consultados de manera rápida directamente en el formulario, conectándose a las entidades que están registradas, vehículos y sus características configuradas. Esta mejora va a permitir reducción de errores de escritura, mayor velocidad en la recepción y permite que el asesor de servicio se concentre en detallar las particularidades de la recepción que son comunicadas por el conductor y no son detalladas en la orden de trabajo inicial enviada desde la entidad a la serviteca antes de la recepción, además de permitir el envío de notificaciones oportunas al área administrativa y acelerar los procesos de creación de ordenes de trabajo por parte de dicha área.

---

## HU_001 — Creación de la Recepción del Vehículo

**Como** Asesor de servicio.
**Quiero** Realizar la creación de recepciones de vehículos de manera asistida consultando estrictamente por placa o sigla.
**Para** Agilizar el ingreso, eliminar errores de escritura y notificar oportunamente a coordinación y taller.

### Precondiciones

**1** El usuario debe tener una sesión activa con el rol de Asesor de servicio y su firma digital configurada. 

**2** La base de datos de vehículos y entidades debe estar previamente parametrizada.

### Especificación Técnica de Comportamiento

 **1** **Búsqueda Estricta:** El sistema permitirá buscar vehículos estrictamente por placa o sigla. No se admite la búsqueda por entidad ni por contrato para evitar listas masivas.

 **2** **Autocompletado Asíncrono:** Al ingresar la placa o sigla, el sistema consultará y autocompletará en modo de solo lectura los campos: Entidad, Marca, Clase, Modelo y Color.    
 
 **3.** **Selector de Flujo (Orden Externa):** El formulario incluirá un control tipo checkbox para indicar si el vehículo ingresa con orden externa o sin orden.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** digitar placa/sigla y confirmar → autocompleta los datos; cargar evidencia (si aplica) → guardar. El flujo principal no supera tres clics.
**2.** **Autocompletado y precarga:** Entidad, Marca, Clase, Modelo, Color y último kilometraje se precargan en solo lectura.
**3.** **Confirmaciones en tiempo real:** la búsqueda del vehículo y la validación del kilometraje se ejecutan de forma asíncrona, sin recargar la pantalla.
**4.** **Firma interna automática:** la firma del asesor se toma del perfil autenticado, sin botón de firma manual.

### Criterios de Aceptación y Validaciones

**1.** **Validación de Kilometraje (Requerido):** El sistema validará el kilometraje actual en tiempo real. Si el valor ingresado es menor al anterior o no es válido, emitirá una alerta emergente (popup).  

**2.** **Gestión de Vehículo No Registrado:** Si la placa o sigla no está registrada, el recepcionista podrá ingresar los datos básicos como placa, color, modelo o disponibles; el sistema alertará a coordinación y el vehículo no estará disponible para operar hasta su validación. 

**3.** **Flujo Sin Orden Externa:** Si se marca el ingreso sin orden, se habilita un flujo de diagnóstico que requiere autorización administrativa posterior.  

**4.** **Carga de Evidencia:** Si se marca el ingreso con orden externa, será obligatorio cargar la imagen del documento para guardar la recepción.


### Matriz Delta de Cambios

**[ADDED]**
- Checkbox "Ingresa con orden externa" con carga de evidencia (archivo, foto o cámara).
- Autocompletado del último kilometraje registrado como dato de solo lectura.
- Notificaciones multicanal (correo con PDF, WhatsApp y alerta visual en campanita).
- Inmutabilidad de la recepción aprobada.
- Flujo de vehículo no registrado con registro de datos disponibles y bloqueo hasta validación de coordinación.

**[MODIFIED]**
- Búsqueda: estrictamente por placa o sigla, eliminando entidad y contrato como filtro principal.
- Integración de las consultas de entidad y de vehículo (HU_002 y HU_003 originales) como componente de autocompletado dentro de HU_00**1.**
- Validación de kilometraje: ahora con alerta emergente (popup) bloqueante y mensaje del último valor registrado.
- Firma del asesor: se toma automáticamente del perfil autenticado.

**[REMOVED]**
- Regla de negocio que exigía orden de trabajo enviada con antelación por la entidad (la OTe deja de ser obligatoria).
- Búsqueda por entidad o por contrato.
- Botón de firma manual para el personal interno.

---

## HU_002 — Diligenciamiento de Formatos e Inventario por Entidad

**Como** Asesor de servicio  
**Quiero** diligenciar los inventarios y formatos específicos de cada entidad  
**Para** asegurar que se visualicen los campos requeridos según el contrato y realizar una inspección básica al momento del ingreso o salida.

### Precondiciones

 **1** Usuario autenticado con rol Asesor de Servicio 
 
 **2** El vehículo debe pertenecer a una entidad con contrato vigente parametrizada previamente en el sistema.  
 
 **3** Formulario de recepción y/o entrega en ejecución.

### Especificación Técnica de Comportamiento

**1** **Despliegue Dinámico:** Al identificar la entidad, el sistema despliega automáticamente el formato de ingreso y el inventario simple configurado específicamente para los requisitos de esa entidad.  

**2** **Controles de Chequeo:** Se visualiza una lista de chequeo de inventario (mediante checkboxes) correspondiente a los requerimientos documentales asignados a la institución.

### Criterios UX / Usabilidad

**1.** **Despliegue automático:** el formato e inventario aparecen automáticamente al identificar la entidad, sin clics adicionales.

**2.** **Checkboxes precargados:** la lista de chequeo se muestra lista para marcar, según la configuración de la entidad.

**3.** **Confirmación en tiempo real:** al marcar daños en el esquema 2D, el registro se guarda en el momento sin recargar la pantalla.

### Criterios de Aceptación y Validaciones

**1** **Restricción de Rol:** El Asesor de Servicio se encarga de consumir y diligenciar el formato y el inventario específico asignado a la entidad; no tiene permisos para configurar o alterar el diseño de dichos formatos.  

**2** **Condicionalidad del Inventario:** El registro de la lista de chequeo de inventario será obligatorio dependiendo estrictamente de si la entidad requiere dicho inventario en su configuración asignada.  

**3** **Restricción de Salida:** El formulario de salida debe ser habilitado y diligenciado únicamente cuando la recepción cuente con la aprobación previa del coordinador administrativo.



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

## HU_003 — Firmas Digitales en Formularios

**Como** Asesor de servicio  
**Quiero** Habilitar el espacio de captura de firmas en los formularios de recepción y entrega.
**Para** Formalizar el proceso, asegurar la validación legal del servicio y garantizar la conformidad de las partes.

### Precondiciones

**1.** Usuario autenticado con rol Asesor de Servicio 

**2.** El usuario se encuentra en la etapa final de diligenciamiento de cualquier formulario de ingreso o salida.  

**3.** El asesor de servicio cuenta con una firma configurada en su perfil activo.

### Especificación Técnica de Comportamiento

**1.** **Lienzo de Captura:** El sistema habilita un espacio interactivo de pantalla táctil para la captura de la firma dibujada manualmente por parte del cliente o responsable de la entrega del vehículo.

### Criterios UX / Usabilidad

**1.** **Firma interna automática:** el asesor no requiere acción manual; su firma se aplica desde el perfil.
**2.** **Un solo lienzo para el conductor:** la firma del responsable se captura en un único espacio en pantalla.
**3.** **Confirmación en tiempo real:** la firma capturada se muestra inmediatamente en el formulario sin recargar la pantalla.

### Criterios de Aceptación y Validaciones

**1.** **Firma del Conductor Obligatoria:** El sistema exige de manera obligatoria la firma dibujada del conductor/responsable de la entrega en el espacio habilitado; un lienzo en blanco requerido para el guardado de la recepción.  

**2.** **Automatización de Firma Interna:** La firma del asesor de servicio se toma automáticamente del perfil del usuario autenticado; la captura de firma manual se elimina para el personal interno.  

**3** **Configuración de Firma:** Si el usuario activo no tiene una firma digital configurada, el sistema permite registrar la firma directamente dentro del formulario y la guarda automáticamente, garantizando que en próximos procesos el campo se complete de forma predeterminada y ya no sea necesario volver a ingresarla.