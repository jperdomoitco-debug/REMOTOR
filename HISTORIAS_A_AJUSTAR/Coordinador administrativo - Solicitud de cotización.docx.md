

| Solicitud de cotización |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Solicitar cotización |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Aprobar recepción |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Coordinador administrativo |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Estandarizar la forma en que se solicitan cotizaciones al almacenista. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | servicio |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Solicitar cotización. |  |  |  |

| Situación Actual |
| :---- |
| La solicitud de cotizaciones se realiza actualmente de forma verbal o mediante notas informales entre el área administrativa y la encargada de inventario. Este proceso carece de trazabilidad, estandarización y registro centralizado. Como resultado, se presentan interrupciones operativas, falta de visibilidad sobre el estado de las solicitudes y tiempos de respuesta ineficientes debido a la dependencia de la interacción manual y presencial. |

| Situación Deseada |
| :---- |
| Implementar un proceso estandarizado y digital para la solicitud y gestión de cotizaciones de repuestos. Este modelo busca reemplazar los canales informales por una plataforma de registro centralizado que garantice la trazabilidad de cada requerimiento desde su origen hasta la respuesta final. El nuevo flujo asegurará que todas las solicitudes incluyan la información necesaria desde el primer contacto, evitando reprocesos y consultas adicionales entre áreas. Además, proporcionará visibilidad en tiempo real del estado de cada gestión para todas las partes involucradas. |

**HU\_001 Solicitar cotización**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Solicitar cotización** | **Dado que:** El proceso actual carece de formalidad, registro centralizado y trazabilidad, dependiendo exclusivamente de interacciones verbales o notas informales. **Cuando:** El coordinador administrativo necesite la cotización de uno o más repuestos. **Entonces:** Generará la solicitud de cotización mediante un formulario vinculado a la orden de trabajo, especificando los repuestos requeridos para centralizar la información, eliminar reprocesos y garantizar un seguimiento efectivo. El almacenista necesitará información específica para realizar una cotización efectiva, datos como, entidad y placa y repuestos a cotizar. Regla de negocio: las solicitudes de cotización sólo se desencadenan siempre y cuando el trabajo sea realizado por personal técnico interno. |

