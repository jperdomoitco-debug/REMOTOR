sept 22, 2026

## **Revisión historias de usuario \- REMOTOR \- Diana Rosero y Julio Ruiz**

Invitado [diana.rosero.revolucion@gmail.com](mailto:diana.rosero.revolucion@gmail.com) [Julio Cesar Ruiz](mailto:juliocruizt@gmail.com) [Julián Perdomo](mailto:jperdomo.itco@gmail.com)

Archivos adjuntos [Revisión historias de usuario - REMOTOR - Diana Rosero y Julio Ruiz](https://calendar.google.com/calendar/event?eid=N2VxOHJiZ2s5aWxramU1bGhyNnY0cTZidGYganBlcmRvbW8uaXRjb0Bt)

Registros de la reunión [Transcripción](https://docs.google.com/document/d/165NWzTjaKzExXY87UJgOVHLtLvCP7ZoaHjDmIVg9H64/edit?usp=drive_web&tab=t.e48128ou54mo) [Grabación](https://drive.google.com/file/d/19at7aSrwo6BJzQYf4c_ajt_MZU1mgrWe/view?usp=drive_web) [Grabación 2](https://drive.google.com/file/d/1FHhyO78MR0U6-TEEEBWsPsSkGFt5I7Sn/view?usp=drive_web) 

### **Resumen**

Revisión de recepción de vehículos con ajustes y definición de flujos.

**Revisión de recepción vehicular**  
Ajuste de validaciones de kilometraje. Simplificación de historias de usuario.

**Consultas y roles de taller**  
Ampliación de acceso al jefe de taller. Estandarización de nomenclatura OT.

**Flujos de órdenes internas**  
Automatización de órdenes internas. Definición de consecutivos por contrato.

### **Decisiones**

## Acordada

* **Eliminación de la aprobación de recepciones** Se decide suprimir la historia de usuario de aprobación de recepciones, determinando que el ingreso del vehículo ocurre de manera independiente a la validación administrativa.

* **Estandarización del formato de historias de usuario** Se acuerda conservar el formato estructurado de historias de usuario que incluye rol, precondiciones y criterios de aceptación de alto nivel, excluyendo escenarios de prueba detallados.

* **Ampliación de roles para consulta de vehículos** Se establece que la funcionalidad de consulta de vehículos ingresados esté habilitada tanto para el coordinador administrativo como para el jefe de taller.

* **Restricción de filtros de búsqueda de recepciones** Se determina que la búsqueda estricta de recepciones se realice exclusivamente por placa o sigla, descartando filtros por entidad o contrato.

* **Configuración de esquemas de numeración consecutiva** Se define que el formulario de recepción maneje un consecutivo global único, mientras que las órdenes de trabajo utilicen un consecutivo independiente por cada contrato o entidad.

* **Reinicio de consecutivos para nuevas órdenes** Se estableció que al crear un nuevo contrato, los consecutivos de las órdenes internas deben reiniciarse en ceros y pertenecer de manera exclusiva a una sola entidad.

* **Generación automática de órdenes internas** Se acordó que las órdenes de trabajo internas se deben crear de manera automática en el sistema y no de forma manual.

* **Creación automática ante orden externa** Se determinó que si un vehículo ingresa con una orden de trabajo externa, se creará de forma automática la orden interna asociada.

* **Generación de orden interna sin recepción previa** Se acordó que cuando un vehículo ingresa sin orden externa, de igual forma se debe crear una orden interna con los ítems vacíos para proceder con el diagnóstico por parte del jefe de taller.

* **Procedimiento para diagnósticos adicionales** Se estableció que ante la necesidad de un repuesto o elemento adicional durante la ejecución, se debe generar un nuevo diagnóstico adicional o versión sin eliminar el diagnóstico inicial.

* **Excepción de órdenes internas para garantías** Se acordó que las garantías constituirán el único caso en el cual no se creará una orden de trabajo interna automática, manejándolo mediante un indicador o checkbox específico.

* **Entrega de ajustes de historias** Se acordó entregar los ajustes de las historias de usuario de recepción y coordinación el próximo día viernes.

### **Próximos pasos**

- [ ] \[El grupo\] Actualizar historias de usuario: Ajustar el formato de las historias de usuario siguiendo la estructura de precondiciones y criterios de aceptación, eliminando la historia sobre aprobación y consolidando los casos de orden externa.

- [ ] \[DIANA\] Revisar historias de usuario: Validar y verificar las versiones actualizadas de las historias de usuario una vez sean cargadas en el sistema.

- [ ] \[Julio Cesar Ruiz\] Informar a Julián: Comunicar a Julián los acuerdos tomados respecto a los cambios en la documentación y el flujo de los procesos.

- [ ] \[El grupo\] Modificar módulos operativos: Incluir al jefe de taller en el módulo de consulta y establecer el flujo de notificación desde la coordinación hacia el taller para cada ingreso de vehículo.

- [ ] \[Julio Cesar Ruiz\] Especificar consecutivos: Registrar en las historias de usuario que el formulario de recepción maneja un consecutivo único e independiente del de las órdenes de trabajo internas. Detallar que dicho consecutivo de recepción se reinicia con cada nuevo contrato.

- [ ] \[Julio Cesar Ruiz\] Automatizar creación órdenes: Eliminar de la documentación técnica la mención a la creación manual de órdenes de trabajo. Ajustar las especificaciones para que el sistema genere la orden de forma automática al registrar el ingreso del vehículo.

- [ ] \[Julio Cesar Ruiz\] Definir criterios consulta: Refinar las historias de usuario para diferenciar los criterios de aceptación en los módulos de consulta según el perfil del usuario. Especificar los requisitos para la obtención de datos básicos del vehículo y el historial de órdenes asociadas.

- [ ] \[Julio Cesar Ruiz\] Ajustar historias usuario: Finalizar los ajustes en las historias de usuario de recepción y coordinación según los comentarios recibidos. Incluir las modificaciones necesarias derivadas del nuevo formato y contexto.

- [ ] \[Julio Cesar Ruiz\] Subir entregables: Cargar la versión dos de las historias de usuario ajustadas en la carpeta de entregables del proyecto para garantizar la trazabilidad. Asegurar que el material incluya todas las correcciones solicitadas.

- [ ] \[Diana\] Compartir documentación: Finalizar los diagramas de flujo y el análisis de los procesos mencionados. Subir y enviar estos documentos al equipo para facilitar la conexión de los procesos.

- [ ] \[El grupo\] Reunión seguimiento: Programar y asistir a la sesión de seguimiento el viernes a las 3 de la tarde. Revisar en conjunto los ajustes realizados y el contexto final de las historias de usuario.

### **Detalles**

* **Revisión del formulario de recepción de vehículos y órdenes externas**: Julio Cesar Ruiz propuso revisar los cambios realizados en el módulo de recepción de vehículos, enfocándose en la inclusión de una casilla de verificación para determinar si el ingreso cuenta con una orden de trabajo externa. DIANA planteó el problema de que algunas entidades no utilizan el sistema contractualmente, por lo que, a pesar del deseo futuro de que las entidades carguen el documento directamente, DIANA solicitó mantener por el momento una notificación manual a la coordinación como solución consensuada.

* **Validaciones de kilometraje y criterios de usabilidad**: Julio Cesar Ruiz expuso las validaciones implementadas para el kilometraje, tales como la aparición de alertas ante valores negativos o vehículos no registrados en la base de datos. Asimismo, Julio Cesar Ruiz incorporó criterios de usabilidad (flujo menor a tres clics, precarga sincrónica y firma automática del asesor), los cuales DIANA aprobó al considerarlos un aporte útil para el diseño de prototipos.

* **Estandarización en la nomenclatura de las órdenes de trabajo**: DIANA identificó un error en la diferenciación de las órdenes y solicitó a Julio Cesar Ruiz utilizar la nomenclatura estandarizada con la sigla OT para distinguir entre órdenes de trabajo internas y externas. Julio Cesar Ruiz aceptó realizar esta corrección en la documentación técnica.

* **Simplificación de los criterios de aceptación frente a escenarios de prueba**: DIANA argumentó que las historias de usuario redactadas por Julio Cesar Ruiz contenían demasiados escenarios de prueba detallados (como manejo de decimales, espacios o inyecciones SQL) que corresponden al equipo de control de calidad (QA). DIANA instruyó que los criterios de aceptación deben ser concisos (por ejemplo, validar que el kilometraje sea un número entero mayor a cero y superior al anterior), y Julio Cesar Ruiz acordó eliminar los casos excepcionales detallados de las historias de usuario.

* **Aclaración sobre la inmutabilidad y el estado de aprobación de las recepciones**: DIANA corrigió un malentendido conceptual, señalando que la coordinación administrativa no "aprueba" las recepciones ya que el ingreso del vehículo ocurre de forma independiente a las órdenes. Respecto al concepto de "inmutabilidad", DIANA y Julio Cesar Ruiz aclararon que este debe significar que una vez creada la recepción, el registro no puede ser eliminado del sistema, asegurando la trazabilidad documental, lo cual llevó a Julio Cesar Ruiz a eliminar los flujos de aprobación erróneos.

* **Consolidación del formato de historias de usuario**: Julio Cesar Ruiz propuso mantener el formato estructurado con precondiciones, especificaciones técnicas y criterios de aceptación que incluye referencias a la interfaz de usuario. DIANA validó este formato como el correcto y sugirió a Julio Cesar Ruiz utilizar herramientas de apoyo como inteligencia artificial para redactar los objetivos generales del rol de recepción.

* **Consulta de vehículos ingresados y asignación de roles**: Julio Cesar Ruiz y DIANA discutieron el acceso al módulo de consulta de vehículos ingresados, acordando que no debe restringirse únicamente a la coordinación administrativa, sino ampliarse también al jefe del taller. DIANA estableció que al registrarse una recepción, el sistema debe notificar al coordinador administrativo, quien posteriormente especificará al jefe del taller si debe proceder con un diagnóstico o con una orden existente.

* **Especificaciones técnicas y filtros para el listado de recepciones**: Julio Cesar Ruiz detalló las especificaciones técnicas del listado de recepciones, incluyendo campos como placa o sigla, entidad, fecha, hora, kilometraje y estado. DIANA y Julio Cesar Ruiz convinieron que la búsqueda debe ser estricta exclusivamente por placa o sigla, excluyendo filtros por entidad o contrato, y mostrando etiquetas visuales para recepciones sin orden externa o vehículos no registrados.

* **Definición de criterios de aceptación para las consultas**: DIANA indicó que los criterios de aceptación para la consulta de recepciones deben asegurar el ingreso de placas válidas y existentes y la recuperación correcta de los datos asociados (marca y modelo). Julio Cesar Ruiz aceptó simplificar dichos criterios omitiendo escenarios de prueba redundantes.

* **Alcance transversal de la función de consulta**: DIANA explicó que la función de consulta operará como un módulo reutilizable para múltiples propósitos solicitados al sistema, tales como traer información básica del vehículo en la recepción, consultar el último ingreso o revisar todo el historial de ingresos de un vehículo en un periodo determinado. Julio Cesar Ruiz tomó nota de estas indicaciones para su aplicación en el desarrollo.

* **Diferenciación de numeración consecutiva entre recepción y órdenes de trabajo**: DIANA advirtió sobre la necesidad de separar los consecutivos en las tablas de la base de datos, explicando al equipo que el formulario de recepción debe poseer un consecutivo único y continuo para todos los vehículos (independientemente de instituciones como policía, medicina legal o MAVI), mientras que la orden de trabajo interna debe generar un consecutivo independiente por cada contrato o entidad. Julio Cesar Ruiz confirmó que esta separación será especificada en el desarrollo.

* **Numeración consecutiva de órdenes de trabajo internas**: DIANA explica que las órdenes internas pertenecen estrictamente a una entidad y deben tener un consecutivo diferente al de los formularios de recepción. Julio Cesar Ruiz y DIANA acuerdan que dicho consecutivo debe reiniciarse a ceros cada vez que se cree un nuevo contrato, pasando por ejemplo del contrato número 001 al contrato número 002 ([00:59:06](?tab=t.e48128ou54mo#heading=h.cqcon5h8m79i)).

* **Creación automática de la orden de trabajo interna**: Julio Cesar Ruiz y DIANA debaten sobre la especificación técnica de comportamiento, acordando eliminar la palabra "manualmente" al referirse a la creación de la orden interna, ya que esta debe generarse de manera automática por el sistema al ingresar el vehículo ([01:00:23](?tab=t.e48128ou54mo#heading=h.nfxeskyb00s4)). DIANA señala que la orden debe traer por defecto datos como el corte, el contrato y la dependencia o entidad correspondiente ([01:02:51](?tab=t.e48128ou54mo#heading=h.eohkb2dim3hi)).

* **Diferenciación en el flujo según la orden de trabajo externa**: Julio Cesar Ruiz plantea un posible conflicto en la creación automática si ingresan vehículos a los cuales no se les gestiona orden de trabajo, tales como vehículos dados de baja o por garantía ([01:08:58](?tab=t.e48128ou54mo#heading=h.c0gbzai191pp)). DIANA aclara que si el vehículo llega con orden externa, se crea automáticamente la orden interna porque ya cuenta con la aprobación de la entidad; en contraste, si llega sin orden, el flujo requiere la intervención del jefe de taller para un diagnóstico ([01:10:17](?tab=t.e48128ou54mo#heading=h.4odae4ll1mdx)).

* **Alineación de conceptos sobre la orden de trabajo interna mediante caso práctico**: Julio Cesar Ruiz comparte su pantalla mostrando un ejemplo en el taller de la policía en el corte 15 dentro del sistema Taller González para unificar conceptos con DIANA respecto a qué se entiende por orden de trabajo interna ([01:13:18](?tab=t.e48128ou54mo#heading=h.4vwms1a65rew)). DIANA confirma que visualizan el mismo documento y aclara el proceso donde el jefe de taller realiza el diagnóstico y la coordinación define los ítems ([01:14:28](?tab=t.e48128ou54mo#heading=h.40y1opmxdel8)).

* **Detalle del flujo para vehículos que ingresan con orden externa**: DIANA proyecta un esquema gráfico explicando que cuando un vehículo (como una Nissan Frontier con logo de policía) ingresa con una orden de trabajo externa que especifica mantenimientos preventivos o repuestos, Brenda en recepción registra los datos básicos (placa ABC 123, kilometraje) y el sistema crea automáticamente la orden interna con el consecutivo correspondiente ([01:16:54](?tab=t.e48128ou54mo#heading=h.y5geosnbrfn2)).

* **Proceso de diagnóstico y registro de ítems para vehículos sin orden previa**: DIANA explica que cuando un vehículo ingresa sin orden externa, el sistema igualmente crea de manera automática la orden de trabajo interna, pero con los ítems vacíos ([01:25:55](?tab=t.e48128ou54mo#heading=h.ox8lx4v1dfo2)). DIANA detalla que en este escenario se le notifica al jefe de taller, Juan Diego, para que realice un diagnóstico detallado y determine los repuestos necesarios (como motor o aceites) antes de enviarlo a la entidad ([01:29:09](?tab=t.e48128ou54mo#heading=h.kiu8eg3z5v1b)).

* **Autorización de la entidad y manejo de diagnósticos adicionales**: DIANA indica que una vez generado el diagnóstico y la cotización en PDF, esta se debe enviar a la entidad (como la policía) para su respectiva autorización ([01:31:39](?tab=t.e48128ou54mo#heading=h.gpq84bujv98i)). Si durante la ejecución de la reparación se detecta la necesidad de un elemento adicional (por ejemplo, una llanta), el jefe de taller debe generar una versión adicional del diagnóstico, pausar el vehículo y solicitar nuevamente la autorización de la entidad ([01:32:51](?tab=t.e48128ou54mo#heading=h.u0ack8g3cy5)).

* **Consecutivos específicos por entidad, contrato y corte**: DIANA detalla mediante ejemplos numéricos que los consecutivos de las órdenes internas avanzan de forma independiente según la entidad (por ejemplo, policía o CBC) y el contrato, independientemente del número de formulario de recepción en el que se encuentre el sistema ([01:36:44](?tab=t.e48128ou54mo#heading=h.tm6aig27foui)). Se menciona como ejemplo el contrato corte 3, donde van en el consecutivo 261 ([01:40:12](?tab=t.e48128ou54mo#heading=h.mxu726fer3r8)).

* **Gestión de vehículos dados de baja y excepciones por garantía**: DIANA explica que si un vehículo ingresa sin orden y la entidad decide no repararlo por estar muy deteriorado, la orden interna creada inicialmente se modifica o se traslada a otra tabla para llevar el conteo de vehículos dados de baja ([01:41:55](?tab=t.e48128ou54mo#heading=h.r299mktn4khh)). Asimismo, DIANA señala que los ingresos por garantía constituyen la única excepción donde inicialmente no se crea una orden de trabajo interna común, sino una orden específica de garantías mediante un selector en el formulario ([01:44:08](?tab=t.e48128ou54mo#heading=h.6n35ems2srn9)).

* **Interfaz de usuario, vistas y automatización de datos en el sistema**: DIANA describe los elementos de usabilidad que les participantes pueden implementar en la vista de la coordinación, tales como menús desplegables, botones de búsqueda de vehículos registrados o notificaciones mediante una campanita ([01:45:57](?tab=t.e48128ou54mo#heading=h.653bo8arrjch)) ([01:47:28](?tab=t.e48128ou54mo#heading=h.39whgh2fshl2)). Al hacer clic en un vehículo notificado, el sistema debe desplegar automáticamente la orden interna y autocompletar datos como modelo, marca, línea y placa ([01:48:27](?tab=t.e48128ou54mo#heading=h.kvdsqjucrdhq)).

* **Cronograma de entrega de historias de usuario y documentación**: Julio Cesar Ruiz confirma que el día viernes tendrían listos los ajustes del formato de las historias de usuario de recepción y coordinación con base en los detalles conversados ([01:52:30](?tab=t.e48128ou54mo#heading=h.x2h4qv3s6b4g)). DIANA solicita que suban la versión 2 a la carpeta de entregables para mantener la trazabilidad y se compromete a compartir su documentación y diagramas de flujo al día siguiente para conectar mejor los procesos ([01:56:03](?tab=t.e48128ou54mo#heading=h.nqvava6ioep6)).

*Revisa las notas de Gemini para asegurarte de que sean precisas. [Obtén sugerencias y descubre cómo Gemini toma notas](https://support.google.com/meet/answer/14754931)*

*Cómo es la calidad de **estas notas específicas?** [Responde una breve encuesta](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=K1udIgGXwMnCnO-_NgD9DxIWOBEQAjIGCIoCIAAYAQg&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) para darnos tu opinión; por ejemplo, cuán útiles te resultaron las notas.*