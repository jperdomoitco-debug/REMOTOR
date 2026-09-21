Punto 1: Habilitación e Inicio de Diagnóstico
---------------------------------------------

DOCUMENTO:

Asesor de servicio - Creación de recepción del vehículo.pdf / Jefe de taller - Creación de diagnóstico de vehículos.pdf

HUS:

**Asesor de servicio** >> HU 005: Notificar al jefe de taller la nueva entrada de vehículo.  
**Jefe de taller** >> HU 001: Creación de diagnóstico del vehículo.

CONTEXTO:

En la HU 005 de Recepción se indica que el Jefe de Taller no podrá iniciar diagnósticos hasta que la recepción esté aprobada por el Coordinador Administrativo. Por otro lado, la HU 001 de Diagnóstico establece que el registro de un diagnóstico requiere obligatoriamente una Orden de Trabajo interna (OTi) previa, y que este diagnóstico requiere aprobación administrativa previa para evitar diagnosticar vehículos no validados.

PREGUNTA:

Mecanismo de habilitación para iniciar el diagnóstico >> ¿La sola creación y existencia de la OT en el sistema habilita automáticamente al taller para diagnosticar, o la OT debe pasar por un estado/bandera explícito de "Aprobada para Diagnóstico" por parte de Administración antes de permitir abrir la pantalla de creación de diagnóstico?

RESPUESTA DEFINITIVA

*   OTe no es obligatoria. OTi sí es obligatoria.
*   Caso A: Vehículo ingresa CON OTexterna (Checkbox = SI)
    
    Estado de OTI: AUTORIZADA PARA DIAGNÓSTICO Y CONFIRMACIÓN
    
    **Mecanismo:** La Administración revisa el PDF/foto adjunto, valida la OT y habilita al Jefe de Taller. El Jefe de Taller realiza el diagnóstico únicamente para confirmar las cantidades e ítems que ya venían prefijados en la OTe. Al confirmar, el vehículo pasa inmediatamente a ejecución de trabajos.
    
*   Caso B: Vehículo ingresa SIN OTexterna (Checkbox = NO)
    
    Estado de OTI: APROBADA PARA DIAGNÓSTICO (PENDIENTE DE OTE)
    
    **Mecanismo:** La Administración abre la OTi "sin ítems" y la aprueba únicamente para evaluación técnica. Esto habilita en la app del Jefe de Taller la opción de crear el diagnóstico. Una vez el Jefe de Taller guarda el diagnóstico, la OTi queda bloqueada en estado **EN ESPERA DE AUTORIZACIÓN DE ENTIDAD**, el vehículo se queda en patio sin intervención alguna, y se envía la propuesta comercial/cotización a la entidad.
    
*   Regla de Negocio en Pantalla (Control de Acceso del Jefe de Taller):
    
    Pantalla del Jefe de Taller: Al ingresar al listado de vehículos en patio, el botón **"Crear Diagnóstico"** estará deshabilitado (gris) si la OTi está en estado REGISTRADA EN RECEPCIÓN O PENDIENTE DE VALIDACIÓN ADMIN.
    
*   Disparo del Evento:
    
    Tan pronto la Coordinación Administrativa valida la entrada en el sistema, el estado de la OTi cambia a habilitado y el sistema dispara automáticamente una alerta/notificación (vía PUSH y/o integración con Bot de WhatsApp) al Jefe de Taller informándole: _"Vehículo \[Placa/Sigla\] habilitado para diagnóstico \[Indica si confirma cantidades de OTe o si es levantamiento de ítems desde cero\]"_.
    

2

Punto 2: Almacenamiento y Transcripción de Audio de Diagnóstico
---------------------------------------------------------------

Guardar audio y queda enlazado a la OT

El archivo de audio original (`.mp3` / `.wav` / `.m4a`) **DEBE almacenarse permanentemente** y quedar disponible para su reproducción dentro de la Orden de Trabajo Interna (OTI), adjunto a la transcripción de texto. **Guardado Máximo por 1 año**, pasado el año este debe eliminarse. El audio no se descarta tras la transcripción, funciona como evidencia técnica/auditoría en caso de discrepancias entre lo dicho por el Jefe de Taller y la transcripción generada por el software.

### 1\. Arquitectura de Almacenamiento e Interfaz

Almacenamiento (Infraestructura):

El archivo de voz grabado desde la App móvil/Web del Jefe de Taller se sube directamente al servidor de almacenamiento en la nube (ej. Google Drive en la carpeta de la OTi correspondiente o Amazon S3/Cloud Storage). En la base de datos de la OTI se guardan dos atributos para el diagnóstico: **URL Audio** (Enlace directo al archivo multimedia) y **Texto Transcripción** (Texto generado mediante el motor de reconocimiento de voz).

Interfaz de Usuario (Vista OTI):

En la pestaña/módulo de Diagnóstico de la OTi, la sección de "Hallazgos Técnicos" mostrará: Un **Reproductor de Audio Embebido** (con botones de Play/Pausa, barra de progreso y velocidad de reproducción 1.5x/2x). Un campo editable de **Texto Transcrito** donde el Coordinador Administrativo o el Jefe de Taller pueden corregir manualmente cualquier error de interpretación del motor de voz (ej. nombres específicos de repuestos técnicos).

### 2\. Regla de Negocio y Utilidad Operativa (Flujo)

Jefe de Taller Graba Nota de Voz

Procesamiento del Sistema: 1\. Almacena Audio mp3/wav en Servidor/Drive. 2\. Ejecuta Transcripción Speech-to-Text.

Registro Final en OTI: Player de Audio para auditar. Transcripción Editable para cotizar.

3

Punto 3: Gestión de Múltiples Diagnósticos y Fases por Técnico
--------------------------------------------------------------

DOCUMENTO:

Jefe de taller - Creación de diagnóstico de vehículos.pdf

HUS:

**Jefe de taller** >> HU 001: Creación de diagnóstico del vehículo >> _Regla: Una OTI puede tener N diagnósticos relacionados._

**Jefe de taller** >> HU 003: Realizar asignaciones de técnicos en los diagnósticos.

CONTEXTO:

La HU 003 explica que cuando un trabajo requiere una nueva fase (ej. eléctrica, mecánica, latonería), el Jefe de Taller debe poder asignar un nuevo técnico o proveedor para el diagnóstico y conservar el historial. Al mismo tiempo, la HU 001 menciona que una OTI puede tener N diagnósticos asociados.

PREGUNTA:

Gestión de múltiples diagnósticos vs. fases con diferentes técnicos >> ¿Cuando el vehículo pasa a una nueva fase o especialidad técnica, el Jefe de Taller debe actualizar el diagnóstico inicial asignando al nuevo técnico, o la buena práctica del flujo exige crear un nuevo registro de diagnóstico adicional vinculado a la misma OT?

RESPUESTA DEFINITIVA

El flujo operacional exige crear un **registro de Diagnóstico Adicional (Nuevo)** vinculado a la misma Orden de Trabajo (OTi). No se debe sobreescribir pero sí es posible añadir algo al diagnóstico.

#### Acción en el Software (Vista Jefe de Taller):

1.  1. En la OTi actual (que consolida la placa y entidad del corte), el Jefe de Taller selecciona el botón **"Diagnosticar"**.
2.  2. Registra los hallazgos (con soporte de nota de voz si aplica).
3.  3. El sistema consolida todos los diagnósticos (N) bajo la misma OTi para efectos del Informe de Actividades, Prefacturación y Control de Saldos.
4.  4. Si se necesita adicionar algo en el diagnóstico se repite el proceso secuencialmente.

Nota importante >> Ítems Fuera de Oferta Económica:

Los diagnósticos en algunas ocasiones suelen contener repuestos o trabajos fuera del contrato inicial. Al ser un nuevo diagnóstico, el sistema puede marcar esos ítems nuevos en amarillo y enviarlos a la Coordinación Administrativa para gestionar su correspondiente autorización previa o adición a la OTe.

4

Punto 4: Protocolo de Detención por Fallas Ocultas de Seguridad
---------------------------------------------------------------

DOCUMENTO:

Jefe de taller - Creación de diagnóstico de vehículos.pdf

HUS:

**HU 001**: Creación de diagnóstico del vehículo >> _Sección: Importante_

CONTEXTO:

En las observaciones de la HU 001 se destaca que un objetivo primordial del diagnóstico es notificar a Administración sobre fallas ocultas que comprometan la seguridad del vehículo.

PREGUNTA:

Protocolo de detención por detección de fallas ocultas >> Al marcar un hallazgo como "Falla Oculta de Seguridad" en el diagnóstico, ¿el sistema debe bloquear preventivamente la ejecución de la OT en el taller a la espera de que la entidad autorice el nuevo presupuesto, o la OT puede continuar ejecutando las actividades previamente autorizadas en paralelo?

RESPUESTA DEFINITIVA: Protocolo de Manejo para Diagnósticos Adicionales

Cuando se detecta un hallazgo nuevo durante el proceso de reparación, el Jefe de Taller genera un Diagnóstico Adicional y lo envía a la Coordinación Administrativa para cotizarlo con la empresa y esperar la nueva autorización/adición de OTe.

CASO A: Independiente (~2%) CONTINÚA

(Lo nuevo NO afecta lo aprobado) -> **Vehículo CONTINÚA en reparación.** Actividades autorizadas siguen su curso. El Adicional queda como "PENDIENTE" para una nueva OTe. Notificación a Coordinación Administrativa.

CASO B: PAUSA OBLIGATORIA - Dependiente / Crítico (~98%) DETENCIÓN

(Lo nuevo frena y/o condiciona lo anteriormente aprobado) -> **Vehículo pasa a estado: PAUSADO/EN ESPERA.** Detención de mano de obra en el vehículo. Notificación URGENTE a Coordinación Admin y Pendiente OTe.

Criterio de Decisión:

"Lo diagnosticado en la adición es indispensable para continuar con la reparación autorizada o para garantizar el funcionamiento correcto de la pieza intervenida."

Comportamiento en el Software:

*   Al guardar el Diagnóstico Adicional, el Jefe de Taller selecciona el Checkbox: `[X] Requiere Pausa por Dependencia Técnica`.
*   La OTi cambia automáticamente a estado: **PAUSADO POR ADICIONAL PENDIENTE**.
*   Se detiene el cronómetro/asignación de trabajo del mecánico asignado.
*   La Coordinación Administrativa recibe la alerta para cotizar de inmediato a la entidad.

Gestión de la Orden Externa (OTe) Adicional o Modificada:

**Modificación / Reemplazo de OTe:** La entidad emite una nueva OTe que reemplaza la anterior sumando los ítems viejos + los ítems nuevos.

**Adición de OTe:** La entidad emite una OTe secundaria/adicional (OTe-2).

**Reactivación Automática:** Una vez cargada la OTe aprobada, la OTi pasa automáticamente de _PAUSADO_ a _AUTORIZADO/EN EJECUCIÓN_, notificando por PUSH/WhatsApp al Jefe de Taller para reanudar el trabajo.

5

Punto 5: Proceso Articulado de Entrega, Control de Calidad e Inventario de Salida
---------------------------------------------------------------------------------

DOCUMENTO:

Asesor de servicio - Creación de recepción del vehículo.pdf / Jefe de taller - Creación de documento de control de calidad.pdf

HUS:

**Asesor de servicio** >> HU 006: Diligenciar formularios de ingreso y salida por entidad / HU 007: Registro de inventario simple en los formularios de recepción

**Jefe de Taller** >> HU 001: Creación de documento de control de calidad.

CONTEXTO:

Las HU\_006 y HU\_007 asignan al Asesor de Servicio la gestión de formularios de salida e inventario simple al finalizar el servicio. Por otra parte, la HU\_001 de Control de Calidad atribuye al Jefe de Taller la verificación del trabajo dentro del formulario de diagnóstico.

PREGUNTA:

Responsabilidad del diligenciamiento del inventario de salida >> ¿El inventario y chequeo físico de salida del vehículo es una responsabilidad del Asesor de Servicio frente al conductor al momento de la entrega presencial, o es realizado previamente por el Jefe de Taller al cerrar el Control de Calidad? ¿La aplicación mostrará automáticamente en pantalla el formato especial de salida?

RESPUESTA DEFINITIVA: Proceso Articulado de Entrega y Salida del Vehículo

Es un procedimiento conjunto y presencial en el patio/zona de entrega entre el Jefe de Taller, el Asesor de Servicio (Recepción) y el Conductor de la entidad.

#### Responsabilidades en el Acto de Entrega Conjunta:

1\. Jefe de Taller (Explicación Técnica):

*   Presenta de manera detallada al conductor qué intervenciones se le realizaron al vehículo (repuestos cambiados, mantenimientos ejecutados y hallazgos corregidos).
*   Entrega o muestra los repuestos sustituidos.
*   Muestra el funcionamiento correcto de los componentes intervenidos.

2\. Asesor de Servicio / Recepción:

*   Verifica el inventario físico final junto al conductor.
*   Captura Evidencia de Salida (fotos/videos del estado final).
*   Muestra y hace firmar el formato de salida correspondiente.

Firma de Salida y Carga de Formatos Específicos por Entidad:

**Visualización Dinámica de Formatos:** Al presionar el botón _"Iniciar Entrega de Vehículo"_, el software consulta la empresa/contrato asociada a la OTI. Si no exige formato especial, muestra el **Formato Estándar**. Si exige formato especial, despliega el **Formato Especial de la Entidad** cargando previamente los datos del vehículo.

**Captura Digital:** Recoge las firmas digitales directamente en pantalla (Conductor y Asesor).

**Consolidación de Evidencia:** Adjunta a la OTi las firmas digitales, las fotos/videos de salida y el PDF generado.