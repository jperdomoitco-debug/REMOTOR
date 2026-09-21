

| Control de saldos de contratos y rentabilidad por orden de trabajo |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Consultar el control de saldos por contrato y rentabilidad por OT |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia general |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Ver un consolidado de todas las órdenes de trabajo por contrato (con detalle de valores, fechas, dependencias, subcontratista, etc.) que cruce los parámetros contables para mostrarme la rentabilidad real y el estado del presupuesto (ejecutado, saldo disponible, % consumido). |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Financiero |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Control de saldos de contratos |  |  |  |

| Situación Actual |
| :---- |
| Para el control de saldos se utiliza un archivo de Excel con una hoja llamada "control de saldos". Se ve un panorama consolidado, pero no se puede medir la rentabilidad real del contrato porque no se están aplicando automáticamente los distintos parámetros contables, deducciones y costos a nivel contractual. |

| Situación Deseada |
| :---- |
| Contar con una vista integrada en el sistema que consolide las órdenes de trabajo bajo cada contrato, permitiendo calcular la rentabilidad exacta y visualizar el estado del presupuesto asignado en tiempo real. |

**HU\_001 Consultar el control de saldos por contrato y rentabilidad por OT**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Consultar el control de saldos por contrato y rentabilidad por OT** | **Dado que:** El Gerente General requiere evaluar la viabilidad financiera de los contratos y tener un control estricto del presupuesto de las entidades. **Cuando:** ingrese a la vista de control de saldos y rentabilidad de un contrato específico. **Entonces:** Se debe calcular y mostrar la rentabilidad real de cada orden de trabajo aplicando los parámetros contables preconfigurados (deducciones y costos, etc), y presentar un consolidado que incluya: El estado de ejecución, fechas datos del vehículo (sigla, placa) dependencia subcontratista (Que realizó o está realizando la ejecución operativa) valores totales, total ejecutado porcentaje de presupuesto consumido  saldo disponible importante: El cálculo de la rentabilidad debe ser real y automatizado. Es mandatorio que el sistema aplique todos los parámetros de deducciones y costos configurados a nivel contractual, solucionando la brecha actual del control manual en Excel. |

