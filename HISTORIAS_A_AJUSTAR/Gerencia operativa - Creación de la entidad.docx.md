

| Creación de la entidad |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación de la entidad |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Creación de dependencia matriz |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Contar con un registro maestro unificado de entidades que actúe como única fuente de información confiable para toda la gestión. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creación de la entidad |  |  |  |

| Situación Actual |
| :---- |
| Actualmente la gestión contractual se maneja mediante del drive en el cual cada carpeta representa a una entidad en específico, en cada carpeta hay un apartado de  ejecución donde reposa un excel llamado control de saldos en el cual se encuentra, la oferta económica y cada una de las órdenes de trabajo asociada al contrato en especifico |

| Situación Deseada |
| :---- |
| Centralizar la información de todas las entidades para tener una visión unificada. Esto facilitará la gestión de varios contratos simultáneos con un mismo cliente y permitirá organizar el seguimiento por áreas o dependencias, adaptándonos de forma flexible a los requerimientos específicos de cada contrato. |

**HU\_001 Creación de la entidad**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación de la entidad** | **Dado que:**  Se requiere tener una centralización de las entidades en el sistema **Cuando:**  Haya un nuevo contrato cuya entidad sea nueva también **Entonces:**  El sistema debe permitir crear una nueva entidad con los siguientes campos: nombre  acrónimo sector administrativo (salud, educación, defensa, Etc) codigo secop |

**HU\_002 Creación de dependencia matriz**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación de dependencia matriz** | **Dado que:** se crea una nueva entidad **Cuando:** se registra la entidad **Entonces:** el sistema debe permitir crear una dependencia matriz o principal con los campos: Nombre de la dependencia Entidad asociada Descripción |

