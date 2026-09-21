

| Identificación de oportunidades |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Registro inicial del proceso |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Filtro de viabilidad |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Equipo Juridico |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Registrar los datos básicos de la licitación y definir si se va a participar o no mediante un filtro de viabilidad estructurado, dejando un historial auditable de la decisión, sin importar el sector económico o industria de la convocatoria. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Licitaciones |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Identificación de oportunidades |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, la búsqueda y análisis inicial se realiza de forma manual, revisando los pliegos para identificar limitantes (limitación a MiPymes, región, fechas críticas) sin un registro centralizado. La decisión estratégica de con qué personería jurídica participar depende del análisis inicial, pero este proceso no queda documentado sistemáticamente. |

| Situación Deseada |
| :---- |
| Implementar un módulo de entrada donde se registren los parámetros clave del proceso y se documente la evaluación inicial de requisitos. El sistema debe permitir registrar la estrategia de personería jurídica seleccionada, operando como un filtro de viabilidad. |

**HU\_001 Registro inicial del proceso**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Registro inicial del proceso** | **Dado que:** hay una nueva licitación pública identificada manualmente en el repositorio oficial de secop ii **Cuando:** ingreso la información principal de la convocatoria en el sistema interno **Entonces:** el sistema crea un nuevo proceso en el tablero kanban dentro de la columna radar en estado de estructuración inicial. Información detallada solicitada: Número único del proceso (ej: lp-001-2026) Objeto contractual detallado Nombre completo de la entidad estatal contratante Presupuesto oficial total y discriminado por lotes (si aplica) Modalidad de selección establecida por la ley (ej: licitación pública, selección abreviada, concurso de méritos) Enlace (link) directo a la plataforma secop ii Fecha y hora límite exacta de presentación de la oferta |

**HU\_002 Filtro de viabilidad**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Filtro de viabilidad** | **Dado que:** No todos los procesos son viables para la empresa **Cuando:** Respondo los criterios básicos de participación y viabilidad **Entonces:** El sistema define si avanzamos a la estructuración o descarta el proceso registrando una causal tipificada. Información detallada solicitada: ¿Exige garantía de seriedad de la oferta y cuál es su porcentaje/vigencia? (sí/no) ¿Requiere requisitos habilitantes específicos o experiencia sectorial exigible? (sí/no) ¿Requiere muestras físicas, pruebas técnicas o visitas obligatorias previas? (sí/no) ¿Se cuenta con la cobertura geográfica y la capacidad instalada para cumplir? (sí/no) Regla de negocio: Ningún proceso puede avanzar a la fase de costeo o estructuración sin haber superado formalmente este filtro de viabilidad. |

