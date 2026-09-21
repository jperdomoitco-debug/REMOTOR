

| Creación de contratos |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación de la maestra de contratos |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Crear el registro maestro de contratos con los datos de los pliegos, desacoplado de cualquier módulo o parámetro contable, para servir como base del ciclo de vida contractual, la parametrización y la asignación presupuestal. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creación de contratos |  |  |  |

| Situación Actual |
| :---- |
| Actualmente no hay un proceso unificado ni una estructura de datos normalizada para dar de alta un contrato; la información depende de la estructura que se cree manualmente en cada carpeta de Drive. Al estar los datos confinados en archivos Excel por cada entidad, se dificulta la consolidación gerencial, el cruce de información a escala y el seguimiento unificado del ciclo de vida contractual. |

| Situación Deseada |
| :---- |
| Para superar las limitaciones actuales, se busca implementar un modelo desacoplado y centralizado enfocado exclusivamente en la creación de la maestra de contratos, sirviendo como base y dependencia para la posterior parametrización, el ciclo de vida de ejecución, los temas contables y la asignación presupuestal. |

**HU\_001 Creación de la maestra de contratos**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación de la maestra de contratos** | **Dado que:**  Se requiere centralizar la información contractual para que sirva como base y dependencia en la ejecución, sin contener parámetros contables nativos. **Cuando:** Se requiere registrar un nuevo contrato en el sistema utilizando la información disponible en los pliegos. **Entonces:** El sistema debe permitir crear un registro en la maestra de contratos con los siguientes campos: Número de Contrato (número oficial impreso en el documento) Número de Proceso (código de la licitación o convocatoria) Objeto del Contrato (descripción de qué se contrató) Tipo de Contratación (forma en que se eligió al ganador, ej. licitación pública) Entidad que Contrata (empresa o institución pública que paga) NIT de la Entidad (número de identificación tributaria de quien contrata) Supervisor o Interventor (persona encargada de vigilar que todo se cumpla) Regla negocio: Una entidad puede tener asociados uno o varios contratos  Importante: Esta representa la maestra, no debe estar acoplada a ningún módulo y/o funcionalidad bajo ninguna circunstancia |

