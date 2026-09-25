# Consultar diagnósticos

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU_001 |  | Consultar los diagnósticos de una Orden de Trabajo interna (OTi) |  |  |  |  |  |  |  |  |  |
| **Rol(es) "Yo como"** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad "Quiero"** |  | Consultar y validar los diagnósticos asociados a una Orden de Trabajo interna (OTi) para alimentar sus líneas |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media | x |  | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 2.0 | 20-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Visualizar múltiples diagnósticos desde la OTi, integrar multimedia con audio y transcripción e identificar los ítems fuera de oferta. |  |  |  |
| 3.0 | 24-09-2026 | Julián Perdomo |  |  | Diana Rosero |  |  | Regla de diagnósticos adicionales sin eliminar el inicial, precondición ajustada sin validación de recepción y criterios de aceptación consolidados. |  |  |  |

## Situación Actual

Actualmente los diagnósticos son representados en un formato físico, diligenciado y transferido al área administrativa para sus respectivas validaciones y el posterior diligenciamiento de las líneas de la orden de trabajo. Este trabajo es en gran parte manual y depende de que el diagnóstico llegue con letra legible.

## Situación Deseada

Se desea que los diagnósticos asociados a una Orden de Trabajo interna (OTi) puedan ser visualizados desde la misma orden, permitiendo:
- Validar hallazgos, ítems y cantidades registrados por el Jefe de Taller.
- Consultar la trazabilidad completa (N diagnósticos por fase o especialidad, sin eliminar los anteriores).
- Reproducir las notas de voz y corregir la transcripción generada por el sistema.
- Identificar visualmente los ítems que quedan fuera de la oferta económica o del contrato vigente.

---

## HU_001 — Consultar los diagnósticos de una Orden de Trabajo interna (OTi)

**Como** Coordinador administrativo,
**Quiero** consultar los diagnósticos asociados a una Orden de Trabajo interna (OTi),
**Para** validar los hallazgos, repuestos y cantidades registrados y alimentar las líneas de la OTi antes de gestionar la cotización con la entidad.

### Precondiciones

**1.** El usuario debe tener una sesión activa con el rol de **Coordinador administrativo**.
**2.** Debe existir una Orden de Trabajo interna (OTi) registrada en el sistema, identificada por su consecutivo.
**3.** El vehículo de la recepción asociada a la OTi debe estar registrado y validado en el sistema.
**4.** Los diagnósticos son registrados previamente por el **Jefe de Taller**; la OTi puede tener cero, uno o N diagnósticos asociados.

### Especificación Técnica de Comportamiento

**1.** **Acceso desde la OTi:** La OTi incluirá un botón "Ver diagnósticos" que lista todos los diagnósticos asociados, sin abandonar la pantalla de la orden.
**2.** **Búsqueda estricta del vehículo/OTi:** La localización de la OTi se realiza estrictamente por placa o sigla; no se admite búsqueda por entidad ni por contrato para evitar listas masivas.
**3.** **Listado y detalle en línea:** Al seleccionar un diagnóstico, el detalle se despliega en la misma pantalla con los hallazgos técnicos, ítems y cantidades, fotografías y datos del técnico, todo en modo solo lectura.
**4.** **Multimedia de diagnóstico:** Si el diagnóstico incluye nota de voz, se muestra un reproductor embebido (Play/Pausa, barra de progreso y velocidad 1.5x/2x) junto con el texto transcrito editable; el Coordinador puede corregir la transcripción sin alterar el diagnóstico.
**5.** **Retención del audio:** El archivo de audio queda enlazado a la OTi como evidencia técnica; se conserva por un periodo máximo de 1 año, tras el cual se elimina automáticamente (la transcripción permanece disponible).
**6.** **Trazabilidad de N diagnósticos:** Una OTi puede tener N diagnósticos (uno por cada fase o especialidad); cada nuevo hallazgo genera un diagnóstico adicional vinculado a la misma OTi, sin eliminar ni sobrescribir el diagnóstico inicial. Se registra log con fecha, hora y usuario que completó cada diagnóstico.
**7.** **Ítems fuera de oferta:** Los repuestos o trabajos que queden fuera de la oferta económica o del contrato se resaltan en amarillo para que la Coordinación gestione su autorización previa o adición a la OTe.

### Criterios UX / Usabilidad

**1.** **Navegación simplificada:** Desde la OTi, un clic abre el listado de diagnósticos y un segundo clic expande el detalle, sin recargar ni salir de la pantalla.
**2.** **Autocompletado y precarga:** La cabecera de la OTi se precarga con placa, entidad, contrato, corte y estado; cada diagnóstico muestra fecha, hora, técnico y estado precargados en solo lectura.
**3.** **Confirmaciones en tiempo real:** La carga del listado y del detalle es asíncrona (sin recarga de pantalla).
**4.** **Filtros en línea:** El listado permite filtrar/ordenar por estado, fecha y técnico sin recargar la pantalla.

### Criterios de Aceptación (Gherkin BDD)

**Escenario 1: Consultar el listado de diagnósticos desde la OTi (caso feliz)**

**Dado que** el Coordinador está autenticado con el rol correspondiente
Y existe una OTi con al menos un diagnóstico asociado
**Cuando** abre la OTi y pulsa el botón "Ver diagnósticos"
**Entonces** el sistema muestra la lista de todos los diagnósticos asociados, cada uno con su estado, fecha, técnico responsable y resumen de hallazgos.

**Escenario 2: Visualizar el detalle de un diagnóstico (caso feliz)**

**Dado que** el listado de diagnósticos de la OTi está visible
**Cuando** el Coordinador selecciona un diagnóstico de la lista
**Entonces** el sistema despliega el detalle en línea con hallazgos técnicos, ítems y cantidades, fotografías y los datos de fecha, hora y técnico, en modo solo lectura.

**Escenario 3: Reproducir la nota de voz y corregir la transcripción (caso feliz)**

**Dado que** el detalle del diagnóstico está abierto y el diagnóstico incluye una nota de voz con su transcripción
**Cuando** el Coordinador reproduce el audio o edita el texto transcrito
**Entonces** el sistema reproduce el audio con los controles disponibles y guarda la corrección de la transcripción sin modificar el diagnóstico.

**Escenario 4: Identificar ítems fuera de la oferta económica (caso feliz)**

**Dado que** el detalle del diagnóstico está abierto y contiene repuestos o trabajos fuera del contrato u oferta vigente
**Cuando** el Coordinador revisa los ítems del diagnóstico
**Entonces** el sistema resalta en amarillo dichos ítems para que la Coordinación gestione su autorización previa o adición a la OTe.

**Escenario 5: Consultar la trazabilidad de diagnósticos múltiples (caso feliz)**

**Dado que** una OTi tiene N diagnósticos registrados por fase o especialidad
**Cuando** el Coordinador consulta los diagnósticos de la OTi
**Entonces** el sistema presenta el historial completo y ordenado cronológicamente, sin eliminar ni sobrescribir los diagnósticos anteriores.

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
- Regla de diagnósticos adicionales sin eliminar ni sobrescribir el diagnóstico inicial.
- Botón "Ver diagnósticos" dentro de la OTi con listado y detalle en línea.
- Reproductor de audio embebido y campo editable de transcripción.
- Marcado en amarillo de ítems fuera de la oferta económica o del contrato.
- Filtros en línea por estado, fecha y técnico.

**[MODIFIED]**
- Precondición ajustada: el vehículo debe estar registrado y validado, sin exigir la validación previa de la recepción por coordinación.
- Criterios de aceptación consolidados a nivel de negocio, en Gherkin conciso.

**[REMOVED]**
- Dependencia del formato físico y de la letra legible del diagnóstico.
- Búsqueda de diagnósticos/OTi por entidad o por contrato.
- Edición del contenido del diagnóstico desde la vista de consulta (solo lectura; únicamente la transcripción es editable).
