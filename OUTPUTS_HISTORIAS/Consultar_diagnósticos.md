# Consultar diagnósticos

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar los diagnósticos de una Orden de Trabajo interna (OTi) |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Consultar y validar los diagnósticos asociados a una Orden de Trabajo interna (OTi) para alimentar sus líneas |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Visualizar múltiples diagnósticos desde la OTi manteniendo la trazabilidad, integrar contenido multimedia con audio y su respectiva transcripción, e identificar con precisión los ítems que se encuentran fuera de oferta. |  |  |  |

## Situación Actual

Actualmente los diagnósticos son representados en un formato físico, diligenciado y transferido al área administrativa para sus respectivas validaciones y el posterior diligenciamiento de las líneas de la orden de trabajo. Este trabajo es en gran parte manual y depende de que el diagnóstico llegue con letra legible.

## Situación Deseada

Se desea que los diagnósticos asociados a una **Orden de Trabajo interna (OTi)** puedan ser visualizados desde la misma orden, permitiendo:
- Validar hallazgos, ítems y cantidades registrados por el Jefe de Taller.
- Consultar la trazabilidad completa (N diagnósticos por fase o especialidad, sin sobrescribir los anteriores).
- Reproducir las notas de voz y corregir la transcripción generada por el sistema.
- Identificar visualmente los ítems que quedan fuera de la oferta económica o del contrato vigente.

---

## HU_001 — Consultar los diagnósticos de una Orden de Trabajo interna (OTi)

**Como** Coordinador administrativo,
**Quiero** consultar los diagnósticos asociados a una Orden de Trabajo interna (OTi),
**Para** validar los hallazgos, repuestos y cantidades registrados y alimentar las líneas de la OT antes de gestionar la cotización con la entidad.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una **Orden de Trabajo interna (OTi)** registrada en el sistema, identificada por su consecutivo único.
**3.** La recepción del vehículo asociado a la OTi debe haber sido validada por la Coordinación administrativa.
**4.** Los diagnósticos son registrados previamente por el **Jefe de Taller** (HU de creación de diagnóstico); la OTi puede tener **cero, uno o N diagnósticos** asociados.

### Especificación Técnica de Comportamiento

**1.** **Acceso desde la OTi:** La OTi incluirá un botón **"Ver diagnósticos"** que lista todos los diagnósticos asociados, sin abandonar la pantalla de la orden.
**2.** **Búsqueda estricta del vehículo/OTi:** La localización de la OTi se realiza estrictamente por **placa o sigla**; no se admite búsqueda por entidad ni por contrato para evitar listas masivas.
**3.** **Listado y detalle en línea:** Al seleccionar un diagnóstico, el detalle se despliega en la misma pantalla (acordeón/modal) con los hallazgos técnicos, ítems y cantidades, fotografías y datos del técnico, todo en **modo solo lectura**.
**4.** **Multimedia de diagnóstico:** Si el diagnóstico incluye nota de voz, se muestra un **reproductor embebido** (Play/Pausa, barra de progreso y velocidad **1.**5x/2x) junto con el **texto transcrito editable**; el Coordinador puede corregir la transcripción sin alterar el diagnóstico.
**5.** **Retención del audio:** El archivo de audio queda enlazado a la OTi como evidencia técnica; se conserva por un **periodo máximo de 1 año**, tras el cual se elimina automáticamente (la transcripción permanece disponible).
**6.** **Trazabilidad de N diagnósticos:** Una OTi puede tener N diagnósticos (uno por cada fase o especialidad: eléctrica, mecánica, latonería, etc.); cada nuevo hallazgo genera un **registro adicional** vinculado a la misma OTi, sin sobrescribir los anteriores. Se registra log con fecha, hora y usuario que completó cada diagnóstico.
**7.** **Ítems fuera de oferta:** Los repuestos o trabajos que queden fuera de la oferta económica o del contrato se resaltan en **amarillo** para que la Coordinación gestione su autorización previa o adición a la OTe.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** Desde la OTi, un clic abre el listado de diagnósticos y un segundo clic expande el detalle, sin recargar ni salir de la pantalla.
**2.** **Autocompletado y precarga:** La cabecera de la OTi se precarga con placa, entidad, contrato, corte y estado; cada diagnóstico muestra fecha, hora, técnico y estado precargados en solo lectura.
**3.** **Confirmaciones en tiempo real:** La carga del listado y del detalle es asíncrona (sin recarga de pantalla), con indicador de progreso mientras se consultan los datos.
**4.** **Filtros en línea:** El listado permite filtrar/ordenar por estado, fecha y técnico sin recargar la pantalla.

### Criterios de Aceptación

**Escenario 1: Consultar el listado de diagnósticos desde la OTi (caso feliz)**

**Dado que** el Coordinador administrativo está autenticado con el rol correspondiente
Y existe una OTi con al menos un diagnóstico asociado
**Cuando** abre la OTi y pulsa el botón "Ver diagnósticos"
**Entonces** el sistema muestra la lista de todos los diagnósticos asociados, cada uno con su estado, fecha, técnico responsable y resumen de hallazgos.

**Escenario 2: Visualizar el detalle de un diagnóstico (caso feliz)**

**Dado que** el listado de diagnósticos de la OTi está visible
**Cuando** el Coordinador selecciona un diagnóstico de la lista
**Entonces** el sistema despliega el detalle en línea con hallazgos técnicos, ítems y cantidades, fotografías y los datos de fecha, hora y técnico, en modo solo lectura.

**Escenario 3: Reproducir la nota de voz y corregir la transcripción (caso feliz)**

**Dado que** el detalle del diagnóstico está abierto
Y el diagnóstico incluye una nota de voz con su transcripción
**Cuando** el Coordinador reproduce el audio o edita el texto transcrito
**Entonces** el sistema reproduce el audio con controles de Play/Pausa y velocidad **1.**5x/2x, y guarda la corrección de la transcripción en tiempo real sin modificar el diagnóstico.

**Escenario 4: Identificar ítems fuera de la oferta económica (caso feliz)**

**Dado que** el detalle del diagnóstico está abierto
Y el diagnóstico contiene repuestos o trabajos fuera del contrato u oferta vigente
**Cuando** el Coordinador revisa los ítems del diagnóstico
**Entonces** el sistema resalta en amarillo dichos ítems para que la Coordinación gestione su autorización previa o adición a la OTe.

**Escenario 5: Consultar la trazabilidad de diagnósticos múltiples (caso feliz)**

**Dado que** una OTi tiene N diagnósticos registrados por fase o especialidad
**Cuando** el Coordinador consulta los diagnósticos de la OTi
**Entonces** el sistema presenta el historial completo y ordenado cronológicamente de todos los diagnósticos, sin sobrescribir los registros anteriores.


**Escenario 6: OTi sin diagnósticos asociados (excepción)**

**Dado que** el Coordinador abre una OTi que no tiene diagnósticos asociados
**Cuando** pulsa el botón "Ver diagnósticos"
**Entonces** el sistema muestra el estado vacío "Aún no hay diagnósticos registrados para esta orden".

**Escenario 7: Audio no disponible por expiración de retención (excepción)**

**Dado que** el audio del diagnóstico superó el periodo máximo de retención de 1 año
**Cuando** el Coordinador intenta reproducir la nota de voz
**Entonces** el sistema muestra la transcripción disponible y la alerta "Audio no disponible por expiración del periodo de retención".

**Escenario 8: Usuario sin permisos de consulta (excepción)**

**Dado que** un usuario sin rol de Coordinador administrativo ni permiso de consulta de diagnósticos
**Cuando** intenta acceder a los diagnósticos de la OTi
**Entonces** el sistema bloquea el acceso y muestra "No tiene permisos para consultar los diagnósticos".

**Escenario 9: Búsqueda restringida a placa o sigla (excepción)**

**Dado que** el Coordinador desea localizar la OTi de un vehículo
**Cuando** realiza la búsqueda
**Entonces** el sistema admite únicamente la búsqueda por placa o sigla y rechaza búsquedas masivas por entidad o contrato.

### Matriz Delta de Cambios

**[ADDED]**
- Botón "Ver diagnósticos" dentro de la OTi con listado y detalle en línea.
- Visualización de N diagnósticos asociados a una misma OTi, con historial cronológico por fase o especialidad.
- Reproductor de audio embebido (Play/Pausa, velocidad **1.**5x/2x) y campo editable de transcripción.
- Marcado en amarillo de ítems fuera de la oferta económica o del contrato.
- Trazabilidad del diagnóstico: log con fecha, hora y usuario/técnico que lo registró.
- Estado vacío para OTi sin diagnósticos y alerta de audio expirado por retención.
- Filtros en línea por estado, fecha y técnico.

**[MODIFIED]**
- Acceso a la información: de documento físico a consulta digital desde la OTi.
- Detalle del diagnóstico: ahora incluye multimedia (fotografías, audio y transcripción).
- Alimentación de líneas de la OT: se precisa que es automática y vinculada a la OTi (no a la OTe).
- Búsqueda de la OTi: estrictamente por placa o sigla; se descarta entidad y contrato como filtro principal.
- Redacción de la narrativa y criterios en formato INVEST + Gherkin atómico.

**[REMOVED]**
- Dependencia del formato físico y de la letra legible del diagnóstico.
- Búsqueda de diagnósticos/OTi por entidad o por contrato.
- Edición del contenido del diagnóstico desde la vista de consulta (la consulta es de solo lectura; únicamente la transcripción es editable).
