# Consultar oferta económica

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar procedimientos y precios por contrato |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Filtrar dinámicamente la maestra de procedimientos |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Consultar y filtrar vehículos |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Consultar y filtrar la oferta económica, vehículos y procedimientos desde el sistema para agilizar la búsqueda de tarifas y la creación de órdenes de trabajo sin recurrir a archivos manuales |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Centralizar la oferta económica facilitando la búsqueda por contrato y placa o sigla, aplicar filtros dinámicos, gestionar precios con o sin IVA y asegurar la trazabilidad completa de los contratos tanto activos como terminados. |  |  |  |

## Situación Actual

Actualmente la gestión de la Oferta Económica (OE) se realiza mediante múltiples archivos de Excel aislados, uno por cada licitación. Esto genera dispersión de información, redundancia de datos y alto riesgo operativo al carecer de una única fuente de verdad. Para verificar los precios o la oferta económica aplicable a un vehículo, el operador debe buscar manualmente dentro del archivo Excel ("control de saldos"): filtrar celdas a mano, buscar la columna correcta de repuestos o mano de obra (con o sin IVA) y validar que corresponda a las características del vehículo, lo que genera demoras e inconvenientes en la operación diaria.

## Situación Deseada

Centralizar la Oferta Económica en una solución digital tipo formulario con consulta filtrada. Permitirá optimizar el proceso, garantizar el acceso a precios actualizados, reducir el tiempo operativo y asegurar una gestión basada en datos consistentes. El sistema debe listar de forma clara y dinámica los procedimientos disponibles con sus valores actualizados de mano de obra y repuestos (con y sin IVA) según el contrato seleccionado, facilitando la creación de órdenes de trabajo de forma precisa.

---

## HU_001 — Consultar los procedimientos y precios por contrato

**Como** Coordinador administrativo,
**Quiero** consultar la oferta económica aplicable a un contrato o a un vehículo,
**Para** obtener los procedimientos vigentes con sus precios de mano de obra y repuestos (con y sin IVA) y crear órdenes de trabajo precisas.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** La Oferta Económica debe estar cargada y parametrizada en el sistema (contratos y procedimientos).
**3.** Debe existir al menos un contrato registrado (activo o terminado).

### Especificación Técnica de Comportamiento

**1.** **Consulta por contrato o por vehículo:** Al seleccionar un contrato específico o ingresar la placa/sigla de un vehículo asociado, el sistema muestra la lista de procedimientos vigentes para ese contrato con los valores de mano de obra y repuestos (con y sin IVA).
**2.** **Contratos informativos:** Los contratos se muestran como dato de **solo lectura**, sin usarse como filtro masivo de vehículos; incluyen tanto contratos **activos** como **terminados** (necesarios para consultar garantías de contratos pasados).
**3.** **Autocompletado:** Al digitar la placa o sigla, el sistema precarga automáticamente el contrato aplicable al vehículo.
**4.** **Relación muchos a muchos:** Un vehículo puede estar vinculado a varios contratos; el sistema los muestra a modo de lectura, indicando bajo cuál contrato se trabajó.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** seleccionar contrato o digitar placa/sigla → ver procedimientos y precios.
**2.** **Autocompletado:** el contrato aplicable se precarga al ingresar la placa o sigla.
**3.** **Confirmación en tiempo real:** la carga de procedimientos y precios es asíncrona, sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Consultar la oferta económica por contrato (caso feliz)**

**Dado que** el Coordinador selecciona un contrato específico
**Cuando** el sistema carga la oferta económica
**Entonces** muestra la lista de procedimientos vigentes para ese contrato con los valores de repuesto y mano de obra, con y sin IVA.

**Escenario 2: Consultar la oferta económica por placa o sigla (caso feliz)**

**Dado que** el Coordinador ingresa la placa o sigla de un vehículo
**Cuando** confirma la búsqueda
**Entonces** el sistema precarga el contrato aplicable y muestra los procedimientos con sus precios.

**Escenario 3: Mostrar contratos activos y terminados (caso feliz)**

**Dado que** el Coordinador consulta los contratos disponibles
**Cuando** despliega la lista de contratos
**Entonces** el sistema muestra los contratos activos y terminados, indicando su estado, en modo solo lectura.

**Escenario 4: Contrato sin oferta económica cargada (excepción)**

**Dado que** se selecciona un contrato sin oferta económica parametrizada
**Cuando** el sistema intenta cargar los procedimientos
**Entonces** muestra el estado vacío "No hay oferta económica cargada para este contrato".

### Matriz Delta de Cambios

**[ADDED]**
- Autocompletado del contrato aplicable desde la placa o sigla.
- Visualización de contratos activos y terminados con su estado, en solo lectura.
- Despliegue de precios de mano de obra y repuestos con y sin IVA por procedimiento.

**[MODIFIED]**
- Oferta Económica centralizada en una solución digital (antes múltiples archivos Excel por licitación).

**[REMOVED]**
- Búsqueda manual en el archivo Excel "control de saldos" (filtrado de celdas a mano).

---

## HU_002 — Filtrar dinámicamente la maestra de procedimientos

**Como** Coordinador administrativo,
**Quiero** filtrar en tiempo real la lista de procedimientos de la oferta económica,
**Para** encontrar rápidamente un procedimiento o ítem y su costo correspondiente.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe estar visible la oferta económica de un contrato.

### Especificación Técnica de Comportamiento

**1.** **Filtro por palabra clave:** Al ingresar una palabra clave (ej. "alternador", "freno", "aceite"), el sistema filtra la lista de procedimientos en tiempo real.
**2.** **Filtro por número de ítem:** También permite buscar por el número de ítem.
**3.** **Resultado en vivo:** Muestra únicamente las coincidencias y sus respectivos costos, sin recargar la pantalla.

### Criterios UX / Usabilidad

**1.** **Mínimo de clics (0 clics):** escribir y filtrar automáticamente, sin botones de búsqueda.
**2.** **Autocompletado:** sugerencias de procedimientos a medida que se escribe.
**3.** **Confirmación en tiempo real:** el filtrado se ejecuta de forma asíncrona.

### Criterios de Aceptación

**Escenario 1: Filtrar por palabra clave (caso feliz)**

**Dado que** se está visualizando la oferta económica de un contrato
**Cuando** el Coordinador ingresa una palabra clave como "alternador", "freno" o "aceite"
**Entonces** el sistema filtra en tiempo real la lista mostrando únicamente las coincidencias y sus costos.

**Escenario 2: Filtrar por número de ítem (caso feliz)**

**Dado que** se está visualizando la oferta económica de un contrato
**Cuando** el Coordinador ingresa el número de un ítem
**Entonces** el sistema muestra el procedimiento correspondiente y su costo.

**Escenario 3: Sin coincidencias de filtrado (excepción)**

**Dado que** se ingresa una palabra clave o número de ítem sin coincidencias
**Cuando** el sistema ejecuta el filtro
**Entonces** muestra el estado vacío "No se encontraron procedimientos".

### Matriz Delta de Cambios

**[ADDED]**
- Filtro dinámico por palabra clave y por número de ítem en tiempo real.
- Estado vacío para búsquedas sin coincidencias.

**[MODIFIED]**
- Maestra de procedimientos ahora consultable y filtrable digitalmente en vivo.

**[REMOVED]**
- Búsqueda manual de la columna de repuestos o mano de obra dentro del archivo Excel.

---

## HU_003 — Consultar y filtrar vehículos

**Como** Coordinador administrativo,
**Quiero** consultar la ficha y asignación de un vehículo filtrando por placa o sigla,
**Para** verificar los contratos a los que está vinculado actualmente.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** La base de datos de vehículos y contratos debe estar parametrizada.

### Especificación Técnica de Comportamiento

**1.** **Búsqueda estricta:** La búsqueda de vehículos se realiza estrictamente por **placa o sigla** como parámetro principal, descartando la búsqueda directa por entidad o contrato para evitar listas masivas.
**2.** **Filtros secundarios:** Marca y cilindraje (CC) se usan únicamente como refinamiento posterior a la búsqueda por placa/sigla.
**3.** **Vinculación de contratos:** Al mostrar un vehículo, el sistema detalla los diferentes contratos a los que está vinculado, en modo solo lectura.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** digitar placa/sigla y ver la ficha del vehículo y sus contratos.
**2.** **Autocompletado:** sugerencias de placa/sigla mientras se escribe.
**3.** **Confirmación en tiempo real:** la búsqueda y el refinamiento se ejecutan de forma asíncrona.

### Criterios de Aceptación

**Escenario 1: Consultar un vehículo por placa o sigla (caso feliz)**

**Dado que** el Coordinador ingresa la placa o sigla de un vehículo
**Cuando** confirma la búsqueda
**Entonces** el sistema muestra la ficha del vehículo coincidente.

**Escenario 2: Refinar por marca o cilindraje (caso feliz)**

**Dado que** se obtuvo un resultado por placa o sigla
**Cuando** el Coordinador refina por marca o cilindraje (CC)
**Entonces** el sistema ajusta los resultados sin recargar la pantalla.

**Escenario 3: Mostrar los contratos vinculados al vehículo (caso feliz)**

**Dado que** el vehículo está vinculado a uno o varios contratos
**Cuando** el Coordinador consulta su ficha
**Entonces** el sistema detalla los contratos a los que está vinculado, en modo solo lectura.

**Escenario 4: Vehículo no encontrado (excepción)**

**Dado que** la placa o sigla digitada no existe en la base de datos
**Cuando** el Coordinador confirma la búsqueda
**Entonces** el sistema muestra el estado vacío "Vehículo no registrado".

**Escenario 5: Bloqueo de búsqueda por entidad (excepción)**

**Dado que** el Coordinador intenta buscar vehículos por entidad como parámetro principal
**Cuando** ejecuta la búsqueda
**Entonces** el sistema no lo permite y exige la búsqueda por placa o sigla.

### Matriz Delta de Cambios

**[ADDED]**
- Búsqueda estricta de vehículos por placa o sigla como parámetro principal.
- Refinamiento secundario por marca y cilindraje (CC).
- Visualización de los contratos vinculados al vehículo en solo lectura.
- Bloqueo de la búsqueda por entidad como parámetro principal.

**[MODIFIED]**
- Consulta multicriterio ajustada: placa/sigla como criterio principal, marca y CC como refinamiento.

**[REMOVED]**
- Búsqueda directa de vehículos por entidad o contrato como parámetros principales.
