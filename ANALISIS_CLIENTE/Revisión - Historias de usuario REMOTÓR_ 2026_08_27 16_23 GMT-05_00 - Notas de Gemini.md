ago 27, 2026

## **Revisión \- Historias de usuario REMOTÓR**

Invitado [diana.rosero.revolucion@gmail.com](mailto:diana.rosero.revolucion@gmail.com) [Julio Cesar Ruiz](mailto:juliocruizt@gmail.com) [Julián Perdomo](mailto:jperdomo.itco@gmail.com)

Archivos adjuntos [Revisión - Historias de usuario REMOTÓR](https://calendar.google.com/calendar/event?eid=MW9sMW1uNTNic3J0MGJjbXFhamxrbm1obHEganBlcmRvbW8uaXRjb0Bt)

Registros de la reunión [Grabación](https://drive.google.com/file/d/1C1SMvJFFhROUpP8anbqsfgybX-ARKhNp/view?usp=drive_web)&nbsp;

&nbsp;

&nbsp;

### **Resumen**

Definimos flujos operativos para gestión vehicular con requerimientos de validación, automatización de notificaciones y prototipado funcional básico.

**Automatización y validación vehicular**  
Se automatizará la carga de datos vehiculares mediante placa o sigla. El sistema validará estrictamente el kilometraje ingresado para evitar errores de registro.

**Gestión, estados y firmas**  
Se implementará un módulo CRUD para estados del vehículo y gestión de documentos externos. La firma digital del conductor será obligatoria en cada proceso.

**Flujos, notificaciones y prototipado**  
Los vehículos sin orden externa activarán alertas de coordinación para su diagnóstico. Se presentará un modelo funcional tipo wireframe ante la gerencia próximamente.

&nbsp;

&nbsp;

### **Decisiones**

## Acordada

* **Consulta de vehículos automática** La consulta de datos del vehículo debe ser automática y de solo lectura, activada mediante el ingreso de la placa o la sigla.

* **Validación de kilometraje implementada** Se implementa una regla de validación de kilometraje que genera una alerta cuando el valor ingresado es menor al registrado previamente.

* **Flujo para vehículos no registrados** El proceso para vehículos no registrados requiere que el recepcionista ingrese los datos disponibles y notifique a la coordinación, dejando el vehículo bloqueado hasta que sea validado administrativamente.

* **Firmas digitales obligatorias** El uso de firmas digitales es obligatorio para el recepcionista y el conductor tanto en el ingreso como en la salida del vehículo.

* **Consecutivo único para órdenes** El consecutivo de las órdenes internas será unificado a nivel general, eliminando la gestión de numeraciones independientes por entidad.

* **Estado de vehículos parametrizables** Los estados del vehículo, incluyendo el estado de baja, serán parametrizados a nivel de base de datos para optimizar la trazabilidad y las consultas.

* **Módulo de documentos configurable** Se implementará un módulo configurable para la carga y gestión de plantillas de documentos y formatos externos.

* **Flujo de trabajo para órdenes externas** El flujo de trabajo se define mediante un checkbox de orden externa: si no se marca, el vehículo pasa por un diagnóstico obligatorio antes de solicitar la orden externa y proceder a la reparación.

* **Métodos de carga de vehículos** El módulo de gestión de vehículos soportará tanto el registro individual (CRUD) como la carga masiva mediante archivos Excel o CSV.

&nbsp;

**Actualizamos la sección Decisiones** con tus comentarios.

Danos tu opinión: [Útil](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=L8VHiTM4r1_MzTbyZR0yDxIROBEBMgUIigIgABgBCA&isGoogler=False) o [Poco útil](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=L8VHiTM4r1_MzTbyZR0yDxIROBEBMgUIigIgABgBCA&isGoogler=False)

&nbsp;

&nbsp;

### **Próximos pasos**

- [ ] \[El grupo\] Actualizar historias de usuario: Incorporar criterios de aceptación y reglas de negocio detalladas en la narrativa. Estructurar los requerimientos técnicos según la metodología discutida.

- [ ] \[El grupo\] Configurar recuperación de datos: Implementar la consulta automática de datos del vehículo al ingresar placa o sigla. Configurar estos campos como de solo lectura para el usuario.

- [ ] \[El grupo\] Validar kilometraje: Desarrollar una validación que compare el nuevo kilometraje ingresado con el anterior. Mostrar una alerta al usuario si el valor es menor o incorrecto.

- [ ] \[El grupo\] Implementar creación de vehículos: Desarrollar un módulo para registrar vehículos manualmente o mediante carga masiva de archivos Excel y CSV. Asegurar que este módulo permita al coordinador validar la información de vehículos nuevos.

- [ ] \[El grupo\] Gestionar órdenes de trabajo: Agregar un selector en la interfaz para indicar si el vehículo tiene o no una orden de trabajo externa. Habilitar un flujo de diagnóstico independiente cuando no exista orden previa.

- [ ] \[El grupo\] Configurar notificaciones: Integrar el envío automático de notificaciones a través de WhatsApp y correo electrónico para las alertas de coordinación. Asegurar que todos los mensajes estén estandarizados según el proceso.

- [ ] \[El grupo\] Parametrizar formatos y estados: Crear un módulo configurable para cargar plantillas de documentos internos y externos. Configurar los estados del vehículo como parámetros editables en la base de datos.

- [ ] \[Julián Perdomo\] Validar placas: Implementar validación en la base de datos para mostrar un mensaje cuando una placa ya exista.

- [ ] \[Julián Perdomo, Julio\] Ajustar historias de usuario: Ajustar las historias de usuario existentes para que incluyan precondiciones y criterios de aceptación claros.

- [ ] \[Julián Perdomo, Julio\] Preparar propuesta: Presentar a la gerencia una propuesta sobre los tiempos y costos del prototipado funcional para la reunión de mañana.

&nbsp;

&nbsp;

### **Detalles**

* **Registro automático de datos del vehículo**: La persona participante DIANA señaló que al digitar la placa o la sigla, los datos del vehículo deben cargarse de manera automática en modo de solo lectura para los campos de entidad, marca, clase, modelo y color. Asimismo, se validó internamente con Luis Miguel y don Edwin que el sistema no debe restringir el ingreso exclusivamente a placa o sigla, sino permitir cualquiera de las dos.

* **Validación estricta del kilometraje**: La persona participante DIANA indicó que el sistema debe validar inmediatamente el kilometraje ingresado cuando la persona usuaria escriba el valor y avance al siguiente campo, mostrando una alerta si el número es menor al registro anterior o si se introduce un valor negativo.

* **Manejo de vehículos no existentes en la base de datos**: La persona participante DIANA explicó que si un vehículo no se encuentra registrado, la persona de recepción podrá completar los datos básicos visibles y enviar una notificación de validación pendiente al área de coordinación. La persona participante Julián Perdomo consultó sobre la relación con la oferta económica, y la persona participante DIANA aclaró que esto ocurre frecuentemente por traslados entre entidades como la Alcaldía, la Policía, Seguridad y Justicia, la Corporación Autónoma Regional del Valle del Cauca (CBC), o zonas aledañas con bases de datos obsoletas. El vehículo permanecerá bloqueado para diagnóstico o reparación hasta que la coordinación valide y guarde la información.

* **Obligatoriedad de las firmas digitales**: La persona participante DIANA especificó que la firma digital es estrictamente obligatoria tanto para la recepción como para la salida del vehículo. La firma de la persona recepcionista (como Brenda) puede automatizarse mediante un botón vinculado a la sesión de la persona usuaria, mientras que la firma del conductor o conductora siempre debe ser obligatoria.

* **Envío de notificaciones a través de canales digitales**: La persona participante DIANA determinó que todas las notificaciones dirigidas al personal de coordinación, jefaturas y áreas involucradas deben realizarse a través de WhatsApp y correo electrónico, debiendo quedar estipulado en los criterios de aceptación.

* **Estructura de órdenes de trabajo interno y cotizaciones**: La persona participante DIANA indicó que las órdenes de trabajo interno mantendrán un único identificador consecutivo vinculado a la entidad correspondiente, evitando separar las órdenes por cada institución de manera independiente. Asimismo, la persona participante DIANA aclaró que el formato actúa inicialmente como una cotización que se ajusta según la aprobación de la entidad antes de iniciar formalmente la reparación con la orden de trabajo externa.

* **Estados del vehículo y gestión por medio de módulos CRUD**: La persona participante DIANA solicitó que el sistema incorpore un módulo CRUD para la gestión de vehículos con estados configurables, tales como activo, de baja, registrado, sin orden, en diagnóstico, diagnosticado, orden aprobada, en reparación, finalizado el ajuste y entregado. La persona participante DIANA indicó que el estado de baja permite mantener la trazabilidad histórica sin saturar las consultas activas.

* **Parametrización de formatos y documentos externos**: La persona participante DIANA solicitó un módulo completamente configurable que permita cargar archivos en formato Excel o documentos externos enviados por las entidades para la gestión de ingresos, salidas y otros formatos como actas o controles de saldo.

* **Flujo operativo para vehículos sin orden de trabajo externa**: La persona participante DIANA detalló el flujo cuando un vehículo ingresa sin orden externa mediante un cuadro de selección (checkbox): la persona recepcionista registra los datos, generando una alerta para el área de coordinación y permitiendo ordenar la realización de un diagnóstico en el taller. Una vez finalizado el diagnóstico, la persona participante DIANA explicó que se solicita la autorización y la orden externa a la entidad (como Policía, Medicina Legal u otras), la cual se adjunta al sistema para desbloquear y proceder con la reparación.

* **Compartir documentación del análisis y correos electrónicos**: La persona participante DIANA solicitó las direcciones de correo electrónico de la persona participante Julián Perdomo (jperdomo.itco@gmail.com) y la persona participante Julio César Ruiz Téllez (juliocruist@gmail.com) para compartirles el documento de análisis con permisos de edición y lectura como soporte de lo conversado.

* **Nivel de detalle en las historias de usuario**: La persona participante DIANA aconsejó que las historias de usuario incluyan precondiciones y criterios de aceptación detallados y globales para evitar errores de validación durante el desarrollo, aplicando esta directriz a todos los módulos del sistema.

* **Expectativas de prototipado para la reunión con gerencia**: La persona participante DIANA recomendó que para la reunión con la gerencia no se requiere un prototipo altamente detallado ni finalizado con diseñador gráfico, sino un modelo funcional básico tipo wireframe que permita visualizar el flujo y recorrido de las pantallas. La persona participante DIANA sugirió estimar los costos y tiempos de desarrollo del prototipado para presentarlos ante la gerencia.

&nbsp;

&nbsp;

*Revisa las notas de Gemini para asegurarte de que sean precisas. [Obtén sugerencias y descubre cómo Gemini toma notas](https://support.google.com/meet/answer/14754931)*

*Cómo es la calidad de **estas notas específicas?** [Responde una breve encuesta](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=L8VHiTM4r1_MzTbyZR0yDxIROBEBMgUIigIgABgBCA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) para darnos tu opinión; por ejemplo, cuán útiles te resultaron las notas.*