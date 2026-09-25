# Gestión de oferta económica

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Actualizar la maestra de procedimientos y precios |  |  |  |  |  |  |  |  |  |
| HU_002 |  | Registrar vehículos nuevos y asociarlos al contrato |  |  |  |  |  |  |  |  |  |
| HU_003 |  | Vincular vehículos existentes a múltiples contratos |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Importar las ofertas económicas mediante una plantilla de Excel con un formato común, para centralizar la maestra de procedimientos, registrar los vehículos y asociar los precios específicos (repuestos y mano de obra) a cada contrato |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Gestión de oferta económica. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Carga masiva de la oferta económica mediante plantilla estandarizada, actualización de la maestra de procedimientos, registro de vehículos y vinculación de una misma placa a múltiples contratos. |  |  |  |

## Situación Actual

Para la operación y las órdenes de trabajo se maneja un archivo de Excel ("control de saldos") donde se encuentra la oferta económica. Cada contrato o entidad puede entregar su oferta en un formato distinto, lo que obliga a depender de ese archivo externo y de procesos manuales para identificar los vehículos, los procedimientos y los precios al momento de operar.

## Situación Deseada

Contar con un módulo en el sistema que reciba un archivo Excel estandarizado (un formato común para todas las ofertas, sin importar la entidad de origen). Al subir este archivo, el sistema debe poblar automáticamente la maestra de procedimientos, registrar los vehículos (con placa, sigla, marca y cilindraje) y asociar tanto los vehículos como los precios a su respectivo contrato, soportando que una misma placa pertenezca a múltiples contratos simultáneamente.

---

## HU_001 — Actualizar la maestra de procedimientos y precios

**Como** Coordinador administrativo,
**Quiero** cargar un archivo Excel estandarizado con la oferta económica de un contrato,
**Para** actualizar automáticamente la maestra de procedimientos y asociar los precios de repuestos y mano de obra al contrato correspondiente.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una plantilla Excel estandarizada con la información de la oferta económica.
**3.** El contrato al que pertenece la oferta debe estar registrado en el sistema.

### Especificación Técnica de Comportamiento

**1.** **Carga masiva:** El sistema procesa un formato común de Excel, válido para todas las entidades.
**2.** **Inserción y actualización:** El sistema inserta los ítems que no existan en la maestra de procedimientos y asocia los valores monetarios de repuestos y mano de obra al contrato específico.
**3.** **Actualización de precios:** Los ítems ya existentes se actualizan con los nuevos valores asociados al contrato cargado.
**4.** **Trazabilidad:** Se registra la fecha, hora, usuario y archivo cargado en cada importación.
**5.** **Validación de formato:** Si el archivo no corresponde al formato estandarizado, el sistema rechaza la carga e indica el error.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** seleccionar el archivo y confirmar; la carga se procesa sin reescribir datos.
**2.** **Autocompletado y precarga:** la plantilla descargable facilita el diligenciamiento por parte de la entidad.
**3.** **Confirmación en tiempo real:** el resultado de la importación se confirma sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Cargar la oferta económica de un contrato (caso feliz)**

**Dado que** el Coordinador dispone del archivo Excel estandarizado de un contrato
**Cuando** sube el archivo al módulo de carga masiva
**Entonces** el sistema procesa el formato común y asocia los precios de repuestos y mano de obra al contrato.

**Escenario 2: Insertar ítems nuevos en la maestra (caso feliz)**

**Dado que** el archivo contiene procedimientos que no existen en la maestra
**Cuando** el sistema procesa la carga
**Entonces** inserta los nuevos ítems y los asocia al contrato específico.

**Escenario 3: Actualizar precios de ítems existentes (caso feliz)**

**Dado que** el archivo contiene un ítem ya existente con un valor distinto
**Cuando** el sistema procesa la carga
**Entonces** actualiza el precio del ítem para el contrato cargado.

**Escenario 4: Archivo con formato no estandarizado (excepción)**

**Dado que** el archivo no corresponde al formato común de la plantilla
**Cuando** el Coordinador intenta cargarlo
**Entonces** el sistema rechaza la carga e indica el error a corregir.

### Matriz Delta de Cambios

**[ADDED]**
- Carga masiva mediante plantilla Excel estandarizada (formato común para todas las entidades).
- Inserción y actualización automática de la maestra de procedimientos y precios.
- Trazabilidad de la importación (fecha, hora, usuario y archivo).
- Validación de formato con rechazo de archivos no estandarizados.

**[MODIFIED]**
- Oferta económica: de archivo Excel externo manual a módulo digital de carga centralizada.

**[REMOVED]**
- Dependencia del archivo "control de saldos" y de la digitación manual de procedimientos y precios.

---

## HU_002 — Registrar vehículos nuevos y asociarlos al contrato

**Como** Coordinador administrativo,
**Quiero** que el sistema registre los vehículos nuevos detectados durante la carga de la oferta,
**Para** asociarlos al contrato y habilitarles la oferta económica correspondiente.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe estar en curso el procesamiento de un archivo de oferta económica.
**3.** La base de datos de vehículos debe estar disponible.

### Especificación Técnica de Comportamiento

**1.** **Lectura de propiedades:** Al procesar las filas del archivo, el sistema lee las propiedades del vehículo (placa, marca, cilindraje y sigla).
**2.** **Validación de existencia:** El sistema valida si la placa ya existe en la base de datos.
**3.** **Creación de vehículo:** Si la placa no existe, el sistema crea el vehículo y lo asocia al contrato actual para habilitarle la oferta económica.
**4.** **Sin duplicados:** Si la placa ya existe, el sistema no crea un vehículo duplicado.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** el registro de vehículos se ejecuta de forma transparente durante la carga del archivo.
**2.** **Confirmación en tiempo real:** el resultado de la creación y asociación se confirma sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Registrar un vehículo nuevo desde la carga (caso feliz)**

**Dado que** el sistema procesa las filas del archivo de oferta
**Cuando** lee las propiedades de un vehículo cuya placa no existe
**Entonces** crea el vehículo y lo asocia al contrato actual para habilitarle la oferta económica.

**Escenario 2: No duplicar una placa existente (excepción)**

**Dado que** la placa leída ya existe en la base de datos
**Cuando** el sistema procesa la fila del archivo
**Entonces** no crea un vehículo duplicado.

### Matriz Delta de Cambios

**[ADDED]**
- Registro automático de vehículos nuevos desde la carga de la oferta.
- Asociación del vehículo nuevo al contrato para habilitar su oferta económica.
- Control de duplicados por placa.

**[MODIFIED]**
- Identificación de vehículos: de búsqueda manual en Excel a registro automático en la base de datos.

**[REMOVED]**
- Identificación manual de los vehículos de cada oferta.

---

## HU_003 — Vincular vehículos existentes a múltiples contratos

**Como** Coordinador administrativo,
**Quiero** que una placa ya registrada se asocie a un nuevo contrato sin duplicarse,
**Para** que el vehículo pueda operar bajo las condiciones de varias entidades.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una placa ya registrada y asociada a un contrato previo.
**3.** Debe estar en curso el procesamiento de un archivo de oferta de un contrato diferente.

### Especificación Técnica de Comportamiento

**1.** **Relación muchos a muchos:** Un vehículo puede estar vinculado a varios contratos.
**2.** **Asociación sin duplicar:** Al procesar un archivo de un contrato diferente que incluye una placa existente, el sistema asocia la placa al nuevo contrato, sin duplicar la creación del vehículo.
**3.** **Consulta informativa:** El vehículo muestra los contratos a los que está vinculado, en modo solo lectura.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** la vinculación se ejecuta de forma transparente durante la carga del archivo.
**2.** **Autocompletado:** los contratos vinculados al vehículo se muestran precargados en solo lectura.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Vincular una placa existente a un nuevo contrato (caso feliz)**

**Dado que** una placa ya está registrada y asociada a un contrato previo
**Cuando** se procesa un archivo de un contrato diferente que incluye esa misma placa
**Entonces** el sistema asocia la placa existente al nuevo contrato, sin duplicar el vehículo.

**Escenario 2: Vehículo vinculado a múltiples contratos (caso feliz)**

**Dado que** un vehículo está vinculado a varios contratos
**Cuando** el Coordinador consulta su ficha
**Entonces** el sistema muestra los contratos a los que está vinculado, en modo solo lectura.

### Matriz Delta de Cambios

**[ADDED]**
- Asociación de una placa existente a múltiples contratos, sin duplicar el vehículo.
- Visualización en solo lectura de los contratos vinculados al vehículo.

**[MODIFIED]**
- Vínculo vehículo-contrato: de una relación implícita en Excel a una relación muchos a muchos en el sistema.

**[REMOVED]**
- Duplicidad de vehículos al cargar ofertas de contratos diferentes.
