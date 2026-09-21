sept 16, 2026

## **Nueva revisión historias de usuario \- REMOTOR \- Diana Rosero y Julio Ruiz**

Invitado [diana.rosero.revolucion@gmail.com](mailto:diana.rosero.revolucion@gmail.com) [Julio Cesar Ruiz](mailto:juliocruizt@gmail.com) [Julián Perdomo](mailto:jperdomo.itco@gmail.com)

Archivos adjuntos [Nueva revisión historias de usuario - REMOTOR - Diana Rosero y Julio Ruiz](https://calendar.google.com/calendar/event?eid=MnM2ZW80ZW43bDZqOWUydDEzZmFpazNyNmsganBlcmRvbW8uaXRjb0Bt)

Registros de la reunión [Transcripción](https://docs.google.com/document/d/1YWAYIFJ99OMgbYzSdjQO-koF3kXrWLp6Kpb6zk1KOQw/edit?usp=drive_web&tab=t.sv26jfn4824z) [Grabación](https://drive.google.com/file/d/15PKTIlTlbycJ90Ve50aCBPZs5sI6Geb5/view?usp=drive_web)&nbsp;

&nbsp;

&nbsp;

### **Resumen**

La reunión definió criterios técnicos para el ingreso vehicular y la gestión eficiente de garantías mediante historias detalladas.

**Optimización de búsqueda y registro**  
Se decidió limitar la búsqueda de vehículos exclusivamente por placa o sigla para evitar resultados excesivos. El registro de recepción debe automatizar datos y validaciones de kilometraje para mejorar la experiencia operativa.

**Estructuración de procesos y garantías**  
Las historias de usuario deben dividirse en elementos granulares para facilitar las pruebas. Se integró formalmente el módulo de garantías y se clarificó la obligatoriedad de órdenes de trabajo internas para el consumo de repuestos.

**Gestión de diagnósticos y trazabilidad**  
Se estableció que los diagnósticos sin orden externa deben activar un flujo de autorización administrativa. Las notas de voz del taller deberán archivarse durante 6 meses para garantizar la trazabilidad necesaria.

&nbsp;

&nbsp;

### **Decisiones**

## Requiere más debate

* **Periodo de retención de audios** Se aplazó la definición del tiempo exacto de retención de las notas de voz a la espera de la validación gerencial.

&nbsp;

## Acordada

* **Formato y autocompletado en historias de usuario** Se suprimieron los rótulos H1-H3 en las historias de usuario y se configuraron los campos de entidad, marca, clase y color como solo lectura con autocompletado.

* **Criterios de búsqueda de vehículos** La búsqueda de vehículos en el sistema se configurará estrictamente por placa o sigla, descartando la búsqueda directa por entidad o contrato como parámetros principales.

* **Tratamiento de contratos como datos informativos** Los contratos se manejarán únicamente como información de lectura enlazada a las órdenes de trabajo, evitando su uso como filtros de búsqueda operativa.

* **Desglose detallado de historias de usuario** Las historias de usuario deben desglosarse y detallarse de manera independiente por cada tarea específica del sprint en lugar de mantenerse como un bloque general.

* **Gestión de entidad propietaria y facturación** El registro base del vehículo mantendrá una única entidad propietaria, permitiendo que la coordinación administrativa ajuste la entidad de facturación sin alterar los datos del propietario.

* **Configuración de formatos de inventario por entidad** El sistema permitirá configurar y asignar formatos de ingreso y salida personalizados para cada entidad según sus requisitos específicos.

* **Validación estricta del kilometraje de ingreso** Se implementará una validación en tiempo real del kilometraje que emitirá una alerta emergente si el valor ingresado es menor al anterior o inválido.

* **Control de órdenes externas en recepción** El formulario de recepción incluirá un selector para indicar si el vehículo ingresa con orden externa o sin orden para el flujo de diagnóstico.

* **Automatización de la firma de recepción** La captura de firma de la recepcionista se automatizará mediante el perfil de usuario autenticado en lugar de requerir una acción manual de firma.

* **Canales múltiples de notificación de llegada** Las notificaciones de ingreso de vehículos al coordinador administrativo y jefe de taller se enviarán simultáneamente por correo, WhatsApp y alertas internas en la aplicación.

* **Inclusión de la historia de usuario de garantías** Se acordó que la historia de usuario correspondiente al módulo de garantías debe ser incluida en la planificación de desarrollo.

* **Carácter obligatorio de la orden interna** Se estableció que la orden de trabajo interna es obligatoria para el proceso, aclarando que la orden externa no es necesaria para dicho fin.

* **Almacenamiento de notas de voz diagnósticas** Se determinó que las notas de voz del jefe de taller deben almacenarse de manera permanente como soporte asociado a la orden interna.

&nbsp;

&nbsp;

### **Próximos pasos**

- [ ] \[El grupo\] Refinar prototipos: Ajustar la interfaz de usuario basándose en el flujo de búsqueda priorizado por placa.

- [ ] \[El grupo\] Ajustar filtrado: Modificar la lógica de búsqueda para que sea efectiva mediante la placa del vehículo.

- [ ] \[El grupo\] Configurar formatos: Permitir la asignación y edición de formatos de inventario personalizados para cada entidad.

- [ ] \[El grupo\] Validar kilometraje: Desarrollar una validación estricta que genere un aviso cuando el valor ingresado no sea válido.

- [ ] \[El grupo\] Ajustar formulario: Añadir el control de orden externa y eliminar el botón de firma manual para automatizar la asignación.

- [ ] \[El grupo\] Implementar notificaciones: Crear alertas automáticas para asegurar la comunicación efectiva de nuevos vehículos ingresados.

- [ ] \[El grupo\] Refinar historias: Desglosar las tareas de usuario para asegurar que cada criterio de aceptación esté claramente definido.

- [ ] \[Diana\] Clarificar órdenes de trabajo: Actualizar la documentación para especificar claramente la diferencia entre órdenes de trabajo internas y externas. Eliminar toda ambigüedad en las definiciones de las historias de usuario.

- [ ] \[Julián Perdomo\] Detallar historias usuario: Reescribir y detallar las historias de usuario incluyendo criterios de aceptación específicos. Asegurar la ausencia de ambigüedades sobre los tipos de órdenes de trabajo.

- [ ] \[Diana\] Validar retención audios: Consultar con Edwin y Luis Miguel sobre el periodo de retención obligatorio para las notas de voz adjuntas a los diagnósticos. Definir y documentar el tiempo de conservación tras finalizar el contrato.

- [ ] \[Julián Perdomo, Julio\] Ajustar historias usuario: Realizar los cambios solicitados sobre las entregadas. Asegurar que cumplan con los requerimientos revisados.

- [ ] \[Julián Perdomo\] Programar reunión: Agendar el próximo encuentro para mañana a las 3\.

- [ ] \[DIANA\] Compartir documento: Enviar el archivo con el contexto y dudas pendientes una vez se haya terminado y socializado completamente.

- [ ] \[Julián Perdomo, Julio\] Revisar documento: Analizar el material compartido tras recibirlo.

&nbsp;

&nbsp;

### **Detalles**

* **Modificación de historias de usuario y autocompletado en recepción**: Julián Perdomo presenta los cambios realizados en la historia de usuario para la creación de la recepción del vehículo, suprimiendo los formatos anteriores de H1, H2 y H3 para incorporar descripciones detalladas y campos de autoguardado de solo lectura (entidad, marca, clase y color) mediante el ingreso de la placa o sigla. DIANA confirma que este enfoque de autocompletado asíncrono es correcto ([00:00:00](?tab=t.sv26jfn4824z#heading=h.49bsnqq11cev)).

* **Criterios de búsqueda por placa, sigla, entidad y contrato**: Julián Perdomo detalla los campos de filtrado por placa o sigla mediante campos de texto, así como listas desplegables para entidad y contrato. DIANA advierte que realizar búsquedas directas por entidad o contrato generaría listas masivas de miles de registros (como los vehículos de la policía), sugiriendo que la búsqueda principal y más eficiente se centre exclusivamente en la placa o sigla ([00:01:25](?tab=t.sv26jfn4824z#heading=h.hk9u22syzr90)).

* **Relaciones de bases de datos entre entidades y talleres**: DIANA explica que la estructura relacional entre Taller González y las entidades opera mediante contratos de muchos a muchos con una tabla adicional que almacena llaves primarias y atributos, lo que hace inviable utilizar los contratos como filtros de búsqueda principales debido al volumen y multiplicidad temporal. Julián Perdomo coincide en que es más viable limitar la búsqueda a la placa o sigla ([00:07:18](?tab=t.sv26jfn4824z#heading=h.7lnxdzercydu)) ([00:11:27](?tab=t.sv26jfn4824z#heading=h.h7inrc58f98z)).

* **Manejo de contratos activos, históricos y garantías**: DIANA señala que los contratos tienen estados activos o terminados, y que las garantías de vehículos provenientes de contratos pasados requieren mostrar información a modo de lectura informativa, determinando que los números de contrato no deben ser parámetros de búsqueda para el personal de recepción ([00:12:34](?tab=t.sv26jfn4824z#heading=h.e9b3y0ktm4ic)). DIANA aclara además que las siglas aplican exclusivamente para Policía y Seguridad y Justicia, mientras que entidades como Medicina Legal o CBC en Cali no utilizan sigla ([00:14:09](?tab=t.sv26jfn4824z#heading=h.fchro4w928id)).

* **Desglose detallado de historias de usuario por Sprints**: DIANA aconseja separar las historias de usuario generales en elementos granulares de tipo CRUD orientados a Sprints específicos (como crear, modificar o eliminar roles de manera independiente) para facilitar las pruebas del equipo de control de calidad ([00:15:13](?tab=t.sv26jfn4824z#heading=h.36bo1ne3u7f)). Julián Perdomo explica que el formato generalista actual es una propuesta que se puede ajustar al modelo detallado previo ([00:16:39](?tab=t.sv26jfn4824z#heading=h.j51yk15ruj8m)) ([00:19:20](?tab=t.sv26jfn4824z#heading=h.jkzooq8xyxe2)).

* **Facturación y distinción entre propiedad de entidades**: DIANA aclara que entidades como Medicina Legal poseen una relación uno a uno, mientras que los vehículos de Policía y Seguridad y Justicia pueden cruzarse y facturarse bajo diferentes contratos según la orden ([00:20:40](?tab=t.sv26jfn4824z#heading=h.dvrjpzbdg1ts)). DIANA y Julián Perdomo acuerdan que la recepción registra la entidad base (ej., Policía), y la coordinación administrativa gestiona a qué entidad o contrato se factura posteriormente sin alterar la propiedad original del vehículo ([00:26:34](?tab=t.sv26jfn4824z#heading=h.d1av50h5ykel)).

* **Configuración de formatos de inventario por entidad**: Julián Perdomo expone la asignación de formatos de inventario por entidad. DIANA indica que cada institución (Medicina Legal, Policía, CBC) posee formatos y checklists propios, por lo que el sistema debe permitir configurar, cargar o digitalizar dichos documentos en tabletas o dispositivos sin modificar sus diseños institucionales originales ([00:29:34](?tab=t.sv26jfn4824z#heading=h.703vmu3gqefc)).

* **Validación estricta de kilometraje en tiempo real**: Julián Perdomo presenta la validación estricta que compara el nuevo kilometraje ingresado con el registro anterior. DIANA recomienda implementar una alerta emergente (popup) bloqueante cuando el valor sea menor o inválido (como números negativos o decimales), mostrando el último kilometraje registrado (ej., 10\) en lugar de añadir un campo visual adicional para optimizar la experiencia de usuario ([00:32:21](?tab=t.sv26jfn4824z#heading=h.sasnwcgo3ibo)).

* **Ingreso de vehículos sin orden externa y diagnóstico obligatorio**: Julián Perdomo aborda el flujo para órdenes de trabajo externas mediante un checkbox. DIANA aclara que el checkbox sirve para indicar si el vehículo ingresa con orden o sin orden; si ingresa sin orden, se habilita un flujo que notifica a la coordinación administrativa para autorizar un diagnóstico obligatorio, y se establece el procedimiento cuando un vehículo no se encuentra registrado ([00:35:09](?tab=t.sv26jfn4824z#heading=h.3v6k909lfvhz)).

* **Captura de firmas y sistema de notificaciones**: Julián Perdomo discute la captura de firmas para conductores y recepcionistas. DIANA propone eliminar el botón de firma manual para el personal interno, ya que el sistema debe registrar automáticamente la firma según el perfil de usuario activo (ej., Brenda, María, Petra) ([00:38:07](?tab=t.sv26jfn4824z#heading=h.1klkh52g8r2l)). Julián Perdomo y DIANA repasan que las notificaciones al jefe de taller y al coordinador administrativo deben realizarse simultáneamente por correo, WhatsApp, mensajes de texto y alertas visuales en la aplicación ([00:39:23](?tab=t.sv26jfn4824z#heading=h.exa8ajmeacy1)).

* **Refinamiento de criterios de aceptación y subhistorias de usuario**: Julián Perdomo revisa los criterios de aceptación sobre placas, kilometraje y diagnósticos ([00:42:11](?tab=t.sv26jfn4824z#heading=h.fuxkxym7qkg7)). DIANA sugiere dividir los criterios en subhistorias de usuario numeradas (ej., 001.2 para validación de kilometraje) para detallar validaciones estrictas de datos erróneos, y reitera que el diagnóstico obligatorio debe pasar obligatoriamente por la validación previa de la coordinación administrativa ([00:43:40](?tab=t.sv26jfn4824z#heading=h.y71gbgi2dxop)) ([00:46:19](?tab=t.sv26jfn4824z#heading=h.6x8jdplf4i9d)).

* **Criterios faltantes para vehículos inexistentes y sin orden**: DIANA detalla que los criterios de aceptación deben incluir explícitamente el flujo para vehículos no existentes (permitiendo registrar los datos disponibles como placa, color y modelo para notificar a la coordinación) y para vehículos sin orden (mediante un checkbox que despliega la opción de adjuntar archivos o imágenes), facilitando el diseño directo de prototipos de interfaz ([00:48:54](?tab=t.sv26jfn4824z#heading=h.rs9d7fk8urk3)).

* **Presentación parcial del módulo de garantías**: DIANA proyecta pantalla y presenta una entrega parcial de un documento en Excel creado para estandarizar el módulo de garantías ([00:53:52](?tab=t.sv26jfn4824z#heading=h.rn6wixaixz8v)). DIANA demuestra cómo opera la búsqueda por entidad, placa o sigla (ej., vehículo de Medicina Legal con placa COVID 938 o COV938) para recuperar órdenes de trabajo internas, marcas (ej., Chevrolet), totales facturados y kilometrajes de origen ([00:55:15](?tab=t.sv26jfn4824z#heading=h.hhlx9urniex)).

* **Programación de validaciones y cálculo de garantías en Excel**: DIANA expuso una problemática relacionada con la falta de validaciones automatizadas en Excel para determinar la elegibilidad de garantías según el kilometraje o los días transcurridos. DIANA presentó ejemplos específicos como una fecha de salida el 28 y una fecha de ingreso el 30 de septiembre de 2026, con 33 días transcurridos, además de políticas de garantía de baterías por un año y cambios de aceite por 5,000 kilómetros o un año ([00:58:37](?tab=t.sv26jfn4824z#heading=h.prquji8b9ryt)). Asimismo, DIANA explicó que se incorporaron ítems para registrar unidades, costos con el impuesto al valor agregado (IVA) y pérdidas estimadas para el taller. Julián Perdomo preguntó si dicho flujo se validó con Luis, Edwin y Luis Miguel, señalando que la operación anterior dependía de un sistema de tercerización con un tercero llamado DASA ([01:00:54](?tab=t.sv26jfn4824z#heading=h.wbenivrereo)).

* **Gestión de insumos y descuentos a terceros en garantías**: DIANA planteó que, aunque DASA gestiona las garantías como tercero, Taller González frecuentemente suministra insumos adicionales (como baterías, aceite o correas de accesorios con la sigla 27 3803\) que deben descontarse al tercero ([01:00:54](?tab=t.sv26jfn4824z#heading=h.wbenivrereo)). DIANA detalló que se han presentado casos (aproximadamente tres) donde DASA solicita insumos extras, y explicó que utiliza extensiones de Java y scripts en ASCP para buscar órdenes de trabajo ([01:02:06](?tab=t.sv26jfn4824z#heading=h.5xenixi02z5k)). Julián Perdomo consultó sobre el flujo de ingreso vehicular y confirmó que Brenda recibe el vehículo y anota la garantía en las observaciones ([01:08:09](?tab=t.sv26jfn4824z#heading=h.1pf77bucnjv6)). DIANA concluyó que este módulo de garantías debe ser incluido formalmente dentro de las historias de usuario ([01:10:27](?tab=t.sv26jfn4824z#heading=h.4kdk37gutx1m)).

* **Aclaración sobre órdenes de trabajo interna y externa**: DIANA abordó la ambigüedad en las historias de usuario respecto a los tipos de órdenes de trabajo requeridas para iniciar un diagnóstico ([01:12:59](?tab=t.sv26jfn4824z#heading=h.mdl779s6iw7v)). DIANA explicó que las órdenes externas (como el sistema SIGEA de la Policía) a veces ya incluyen detalles de mantenimiento preventivo (como flasher de direccionales, trompo de freno y bombillos para vehículos como una Renault Traffic o una Nissan Frontier), pero la orden de trabajo interna es estrictamente obligatoria para registrar el consumo exacto de repuestos, tales como 7 cuartos de aceite, filtros, baterías o correas ([01:17:25](?tab=t.sv26jfn4824z#heading=h.gvapu8gyt61f)) ([01:21:23](?tab=t.sv26jfn4824z#heading=h.6zpk4hlt75s)). Julián Perdomo y DIANA coincidieron en que se deben eliminar las ambigüedades en la documentación y establecer que la orden externa no es obligatoria, pero la interna sí lo es ([01:17:25](?tab=t.sv26jfn4824z#heading=h.gvapu8gyt61f)) ([01:24:24](?tab=t.sv26jfn4824z#heading=h.1o9oxf5gxi9t)).

* **Almacenamiento y trazabilidad de notas de voz en el diagnóstico**: DIANA planteó la necesidad de definir si las notas de voz grabadas por el jefe de taller para reportar hallazgos y solicitar repuestos deben conservarse temporalmente o guardarse de manera permanente ([01:25:57](?tab=t.sv26jfn4824z#heading=h.1l2zmek89lyl)). DIANA argumentó que estos audios deben almacenarse como respaldo y trazabilidad por un período mínimo de seis meses después de la finalización del contrato para justificar los repuestos solicitados ([01:27:26](?tab=t.sv26jfn4824z#heading=h.nas5i6avo69k)). Ante limitaciones de tiempo mencionadas por Julián Perdomo debido a compromisos universitarios y reuniones, les participantes acordaron concluir la sesión y agendar una nueva reunión para el día siguiente a las 3:00 de la tarde para revisar las historias de usuario entregadas ([01:29:11](?tab=t.sv26jfn4824z#heading=h.uxi7riizofv3)).

&nbsp;

&nbsp;

*Revisa las notas de Gemini para asegurarte de que sean precisas. [Obtén sugerencias y descubre cómo Gemini toma notas](https://support.google.com/meet/answer/14754931)*

*Cómo es la calidad de **estas notas específicas?** [Responde una breve encuesta](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=o9F1KDV9-2YcZRe1qG1JDxIWOBEQAjIGCIoCIAAYAQg&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) para darnos tu opinión; por ejemplo, cuán útiles te resultaron las notas.*