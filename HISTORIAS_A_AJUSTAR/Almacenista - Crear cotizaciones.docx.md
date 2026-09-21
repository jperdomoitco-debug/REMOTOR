

| Crear cotizaciones |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Gestión de solicitudes y comparativas |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Almacenista |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Centralizar y automatizar la gestión de cotizaciones integrándose con el catálogo de ítems y proveedores, para eliminar la tabulación manual y el retrabajo operativo, permitiendo obtener comparativas automáticas y trazabilidad histórica que garanticen decisiones de compra ágiles, auditables y basadas en datos reales. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Compras |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Crear cotizaciones de ítems según los proveedores que está en el módulo de proveedores. |  |  |  |

| Situación Actual |
| :---- |
| El proceso actual de cotización es manual, descentralizado y altamente dependiente de la gestión informal a través de correos electrónicos y llamadas. No existe una integración con un catálogo de proveedores definido, lo que obliga al almacenista a tabular ofertas manualmente en hojas de cálculo externas. Esta fragmentación genera una alta carga operativa, retrabajos, riesgo de error humano y una pérdida total de trazabilidad de los datos históricos de precios y tiempos de entrega. |

| Situación Deseada |
| :---- |
| Centralizar y automatizar el ciclo de cotización dentro de una plataforma unificada. El objetivo es que el sistema permita generar solicitudes estandarizadas a partir del catálogo de ítems y realice la comparativa de ofertas de manera automática. Esto transformará cada gestión de compra en un activo de conocimiento para la empresa, permitiendo decisiones de compra ágiles, auditables y basadas en información histórica real, eliminando el retrabajo operativo. |

**HU\_001: Gestión de solicitudes y comparativas**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Generar solicitud** | **Dado que:** tengo un ítem con stock insuficiente o necesidad de compra.  **Cuando:** seleccione el ítem y marque "Solicitar cotización",  **Entonces:** el sistema listará automáticamente los proveedores registrados para ese ítem y generará el formato de solicitud. |
| **2** | **Comparación ágil** | **Dado que:** he recibido las respuestas de los proveedores.  **Cuando:** ingrese los precios y tiempos entregados.  **Entonces:** el sistema generará una tabla comparativa automática que resalte la mejor opción según precio y tiempo. |
| **3** | **Trazabilidad histórica** | **Dado que:** he seleccionado la oferta ganadora.  **Cuando:** finalice la gestión.  **Entonces:** el sistema guardará automáticamente el resultado de esta comparativa como histórico del proveedor para consultas futuras. |

