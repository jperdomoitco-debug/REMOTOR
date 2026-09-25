# Liquidación de pago a subcontratistas

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Parametrizar el % de pago a subcontratistas |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Calcular la liquidación |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Registrar el soporte del pago |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Liquidar el pago a los subcontratistas que ejecutan la reparación, aplicando un porcentaje parametrizable por contrato sobre lo facturado y descontando los repuestos consumidos del almacén interno; el pago se ejecuta por fuera del sistema y solo se registra su soporte (recibo) |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta | x | Media |  |  | Baja |  |  | **Módulo / Aplicación** | Facturación |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Porcentaje parametrizable por contrato con vigencia e historial, cálculo automático del neto descontando repuestos del almacén interno y registro del soporte de pago con trazabilidad. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Criterios de aceptación consolidados a nivel de negocio, eliminando validaciones de prueba detalladas (decimales y rangos). |  |  |  |

## Situación Actual

El pago al subcontratista se calcula de forma manual: 30% de lo cobrado a la entidad menos el valor de los repuestos del almacén interno. No hay registro sistematizado ni histórico de liquidaciones, lo que expone el proceso a errores de cálculo, pérdida de trazabilidad y dificultad para auditar los pagos ejecutados a terceros.

## Situación Deseada

El sistema calcula la liquidación automáticamente con el porcentaje parametrizado por contrato (con vigencia e historial de cambios) y descuenta los repuestos consumidos del almacén interno registrados contra la Orden de Trabajo interna (OTi). El pago se ejecuta en la plataforma bancaria por fuera del sistema y solo se registra su soporte (recibo), quedando la notificación al subcontratista como un proceso manual. La experiencia de usuario se optimiza con precarga de datos, cálculo en tiempo real y confirmación sin recargar la pantalla.

---

## HU_001 — Parametrizar el % de pago a subcontratistas

**Como** Coordinador administrativo,
**Quiero** parametrizar el porcentaje de pago aplicable a cada contrato/subcontratista con su vigencia,
**Para** calcular la liquidación de forma automática sin depender de un 30% fijo y manual.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Deben existir el contrato y el subcontratista registrados en el sistema.
**3.** El módulo de Facturación debe estar habilitado.

### Especificación Técnica de Comportamiento

**1.** **Porcentaje por contrato/subcontratista:** Cada contrato puede tener un porcentaje de pago distinto al subcontratista; el sistema permite definirlo (por defecto 30%) y su vigencia (fecha de inicio y fin).
**2.** **Valor por defecto:** Si el Coordinador no configura un porcentaje específico, el sistema asigna 30% por defecto.
**3.** **Vigencia:** El porcentaje solo aplica dentro de su vigencia; si no existe un porcentaje vigente, se utiliza el porcentaje por defecto.
**4.** **Contratos informativos (solo lectura):** El contrato se asocia a la parametrización como dato de solo lectura.
**5.** **Historial de cambios:** Cada modificación del porcentaje queda registrada con fecha, hora, usuario, valor anterior y valor nuevo (trazabilidad auditable).
**6.** **Regla de rango:** El porcentaje debe ser un número entero entre 0 y 100.

### Criterios UX / Usabilidad

**1.** **Mínimo de clics (≤ 2 clics):** seleccionar el contrato/subcontratista, ajustar el porcentaje y confirmar.
**2.** **Autocompletado:** el contrato/subcontratista y su porcentaje vigente actual se precargan en el formulario.
**3.** **Confirmación en tiempo real:** el guardado del porcentaje y su vigencia se confirma sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Parametrizar el porcentaje por contrato (caso feliz)**

**Dado que** cada contrato/subcontratista puede tener un porcentaje de pago distinto
**Cuando** el Coordinador configura el contrato y define el porcentaje de pago con su vigencia
**Entonces** el sistema guarda el porcentaje y lo asocia al contrato.

**Escenario 2: Aplicar el porcentaje por defecto (caso feliz)**

**Dado que** no se configura un porcentaje específico para un contrato
**Cuando** el Coordinador guarda la configuración del contrato
**Entonces** el sistema asigna el porcentaje por defecto de 30%.

**Escenario 3: Usar el porcentaje por defecto ante falta de vigencia (caso feliz)**

**Dado que** el contrato no tiene un porcentaje vigente
**Cuando** el sistema calcula la liquidación
**Entonces** utiliza el porcentaje por defecto de 30%.

**Escenario 4: Porcentaje fuera de rango (excepción)**

**Dado que** el Coordinador ingresa un porcentaje fuera del rango permitido (0 a 100)
**Cuando** intenta guardar la configuración
**Entonces** el sistema bloquea el guardado y exige corregir el valor.

**Escenario 5: Registrar el historial de cambios (caso feliz)**

**Dado que** se modifica el porcentaje de un contrato
**Cuando** el sistema guarda la modificación
**Entonces** registra en el historial la fecha, hora, usuario, valor anterior y valor nuevo.

### Matriz Delta de Cambios

**[ADDED]**
- Porcentaje de pago parametrizable por contrato/subcontratista con vigencia.
- Porcentaje por defecto de 30%.
- Historial de cambios del porcentaje (fecha, hora, usuario, valor anterior y nuevo).

**[MODIFIED]**
- El porcentaje de pago deja de ser un valor fijo manual y pasa a ser un parámetro configurable por contrato.
- Validación de rango expresada como regla de negocio concisa, sin detalle de decimales.

**[REMOVED]**
- Dependencia de un 30% fijo aplicado manualmente a todos los contratos.
- Escenarios de prueba detallados (manejo de decimales y valores negativos).

---

## HU_002 — Calcular la liquidación

**Como** Coordinador administrativo,
**Quiero** calcular automáticamente la liquidación del subcontratista sobre lo facturado, descontando los repuestos consumidos del almacén interno,
**Para** obtener el valor neto a pagar sin cálculos manuales y con trazabilidad del desglose.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una OTi ejecutada por un subcontratista con su total facturado registrado.
**3.** El porcentaje de pago debe estar parametrizado para el contrato (HU_001).
**4.** Los repuestos consumidos del almacén interno deben estar registrados contra la OTi.

### Especificación Técnica de Comportamiento

**1.** **Base de cálculo automática:** El sistema toma el total facturado registrado en la OTi (incluye los valores contractuales: cargos e impuestos), sin permitir la digitación manual de la base.
**2.** **Descuento de repuestos del almacén interno:** Se descuentan exclusivamente los repuestos consumidos del almacén interno y registrados contra la OTi. No se descuentan los repuestos suministrados por el subcontratista ni los comprados por fuera.
**3.** **Fórmula de liquidación:** Neto a pagar = (Total facturado × % subcontratista) − Repuestos del almacén interno.
**4.** **Cálculo en tiempo real:** Al iniciar la liquidación, el sistema precarga el desglose (total facturado, porcentaje aplicado, repuestos descontados y neto a pagar) y lo recalcula automáticamente ante cualquier ajuste, sin recargar la pantalla.
**5.** **Control de neto negativo:** Si el valor de los repuestos supera el porcentaje facturado, el sistema lo advierte antes de continuar.

### Criterios UX / Usabilidad

**1.** **Mínimo de clics (1 clic):** seleccionar la OTi/subcontratista y ver la liquidación calculada.
**2.** **Autocompletado:** total facturado, porcentaje aplicado y repuestos consumidos se precargan en solo lectura.
**3.** **Confirmación en tiempo real:** el neto a pagar se recalcula en vivo ante cualquier cambio de base o de repuestos.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Calcular el valor neto a pagar (caso feliz)**

**Dado que** una OTi fue ejecutada por un subcontratista y tiene su porcentaje parametrizado
**Cuando** el Coordinador inicia la liquidación
**Entonces** el sistema calcula el porcentaje de lo facturado, descuenta los repuestos del almacén interno y muestra el valor neto a pagar.

**Escenario 2: Descontar únicamente repuestos del almacén interno (caso feliz)**

**Dado que** la OTi tiene repuestos consumidos del almacén interno y repuestos suministrados por el subcontratista
**Cuando** el sistema calcula la liquidación
**Entonces** descuenta únicamente los repuestos del almacén interno registrados contra la OTi.

**Escenario 3: Precargar el desglose en solo lectura (caso feliz)**

**Dado que** se inicia la liquidación de una OTi
**Cuando** el sistema precarga los datos
**Entonces** muestra en solo lectura el total facturado, el porcentaje aplicado, los repuestos descontados y el neto a pagar.

**Escenario 4: OTi sin total facturado (excepción)**

**Dado que** la OTi no tiene un total facturado registrado
**Cuando** el Coordinador intenta iniciar la liquidación
**Entonces** el sistema bloquea el cálculo y muestra "No hay valor facturado para liquidar".

**Escenario 5: Neto a pagar negativo (excepción)**

**Dado que** el valor de los repuestos del almacén interno supera el porcentaje facturado del subcontratista
**Cuando** el sistema calcula el neto
**Entonces** advierte al Coordinador que el neto resulta negativo y requiere revisión antes de continuar.

### Matriz Delta de Cambios

**[ADDED]**
- Cálculo automático del neto a pagar con desglose (total facturado, porcentaje, repuestos y neto).
- Base de cálculo tomada del total facturado de la OTi, incluyendo cargos e impuestos contractuales.
- Descuento exclusivo de repuestos consumidos del almacén interno registrados contra la OTi.
- Control de neto a pagar negativo.
- Cálculo en tiempo real sin recargar la pantalla.

**[MODIFIED]**
- El cálculo deja de ser manual y se automatiza sobre la OTi.
- Criterios de aceptación consolidados a nivel de negocio, sin detalle de decimales.

**[REMOVED]**
- Cálculo manual de la liquidación sin registro sistematizado.
- Validaciones de prueba detalladas sobre el formato de los montos.

---

## HU_003 — Registrar el soporte del pago

**Como** Coordinador administrativo,
**Quiero** registrar el soporte (recibo o constancia) del pago ejecutado por fuera del sistema,
**Para** dejar trazabilidad de la liquidación pagada y del comprobante asociado.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** La liquidación debe estar calculada (HU_002).
**3.** El pago debe haber sido ejecutado en la plataforma bancaria por fuera del sistema.

### Especificación Técnica de Comportamiento

**1.** **Adjuntar el soporte:** El Coordinador adjunta el recibo o constancia del pago (imagen o PDF) a la liquidación calculada.
**2.** **Cambio de estado:** Al adjuntar el soporte, la liquidación cambia a estado "Pagada".
**3.** **Inmutabilidad:** Una liquidación en estado "Pagada" queda inmutable; no puede editarse el cálculo ni reemplazarse el soporte sin anular previamente la liquidación.
**4.** **Trazabilidad:** Se registra en el historial de la liquidación la fecha, hora, usuario y soporte adjunto.
**5.** **Notificación manual al subcontratista:** El sistema no notifica automáticamente al subcontratista; la notificación se realiza de forma manual por WhatsApp u otro medio, con el resumen de la liquidación como insumo.

### Criterios UX / Usabilidad

**1.** **Mínimo de clics (≤ 2 clics):** adjuntar el soporte y confirmar el registro.
**2.** **Autocompletado:** los datos de la liquidación y el neto a pagar se precargan al abrir el formulario.
**3.** **Confirmación en tiempo real:** el cambio de estado a "Pagada" y el registro del soporte se confirman sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Registrar el soporte del pago (caso feliz)**

**Dado que** la liquidación está calculada y el pago fue ejecutado en la plataforma bancaria por fuera del sistema
**Cuando** el Coordinador adjunta el recibo o constancia del pago
**Entonces** el sistema registra el soporte y cambia el estado de la liquidación a "Pagada".

**Escenario 2: Registrar la trazabilidad del soporte (caso feliz)**

**Dado que** el soporte fue adjuntado
**Cuando** el sistema confirma el registro
**Entonces** guarda en el historial de la liquidación la fecha, hora, usuario y el soporte adjunto.

**Escenario 3: Notificación manual al subcontratista (caso feliz)**

**Dado que** la liquidación quedó en estado "Pagada"
**Cuando** el Coordinador confirma el registro del soporte
**Entonces** el sistema no notifica automáticamente al subcontratista; la notificación es manual por WhatsApp u otro medio.

**Escenario 4: Confirmar sin soporte adjunto (excepción)**

**Dado que** el Coordinador intenta confirmar el registro sin adjuntar el recibo o constancia
**Cuando** confirma la operación
**Entonces** el sistema bloquea el registro y exige adjuntar el soporte del pago.

**Escenario 5: Editar una liquidación pagada (excepción)**

**Dado que** una liquidación está en estado "Pagada"
**Cuando** el Coordinador intenta modificar el cálculo o reemplazar el soporte
**Entonces** el sistema bloquea la edición y muestra "Liquidación inmutable: anule la liquidación para corregirla".

### Matriz Delta de Cambios

**[ADDED]**
- Registro del soporte de pago (recibo o constancia) con trazabilidad (fecha, hora, usuario y archivo adjunto).
- Cambio de estado de la liquidación a "Pagada".
- Inmutabilidad de la liquidación pagada.

**[MODIFIED]**
- El pago ahora queda registrado y trazable en el sistema.
- Criterios de aceptación consolidados a nivel de negocio.

**[REMOVED]**
- Ausencia de histórico y soporte sistematizado de las liquidaciones ejecutadas.
