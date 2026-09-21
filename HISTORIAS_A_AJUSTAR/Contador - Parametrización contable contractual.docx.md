

| Parametrización contable contractual |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | parametrizar parámetros financieros globales  |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | parametrizar el catálogo de conceptos de costos, deducciones y erogaciones |  |  |  |  |  |  |  |  |  |
| HU\_003 |  | parametrizar costos transversales por contrato |  |  |  |  |  |  |  |  |  |
| HU\_004 |  | parametrizar subpresupuesto por contrato |  |  |  |  |  |  |  |  |  |
| HU\_005 |  | parametrizar estampillas por contrato |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Contador |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | parametrizar y parametrizar a nivel de negocio la información financiera, costos, techos presupuestales y estampillas asociadas a los contratos, |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Financiero |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Realizar la parametrización de impuestos, deducciones y erogaciones contractuales |  |  |  |

| Situación Actual |
| :---- |
| Actualmente se lleva un control superficial del rendimiento contractual teniendo en cuenta únicamente los costos de las órdenes. Esto arroja una rentabilidad parcial, ya que no se tienen en cuenta los impuestos,deducciones y demás elementos transversales que están asociadas al contrato. Dicha omisión de parámetros hace que medir la rentabilidad real sea un proceso mucho más complicado de realizar y propenso a errores de análisis financiero. |

| Situación Deseada |
| :---- |
| Tener un panorama completo, mediante un dashboard o una vista de rentabilidad interna, del comportamiento financiero y la rentabilidad del contrato. Esta visual deberá tener en cuenta todos los parámetros financieros globales, conceptos de costos, impuestos y deducibles transversales. Permitiendo parametrizar los presupuestos y medir fielmente la utilidad generada durante la vigencia y ejecución de los proyectos o mantenimientos asociados. Regla de negocio: Inmutabilidad. Si se modifica cualquiera de los parámetros (ya sean globales o de cualquier otro nivel), no deben verse afectados los contratos a los cuales ya fueron asignados. Debe existir una opción específica en el sistema para esto si se requiere forzar el cambio a los contratos existentes. |

**HU\_001 Parametrizar financieros globales** 

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **parametrizar parámetros financieros globales** | **Dado que:** La organización requiere establecer las políticas y valores financieros transversales que regirán la creación de nuevas contrataciones. **Cuando:** El contador gestiona los parámetros globales en el sistema. **Entonces:** Se debe permitir visualizar y crear los parámetros globales para ser utilizados en los contratos. La información que se debe registrar será la siguiente:  • Nombre del impuesto • Descripcion del impuesto • Valor porcentual |

**HU\_002 Parametrizar el catálogo de conceptos de costos, deducciones y erogaciones**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **parametrizar parámetros financieros globales** | **Dado que:** Un contrato requiere asociar conceptos específicos de costos, retenciones u erogaciones según su naturaleza y marco normativo. **Cuando:** El contador gestiona el catálogo maestro de conceptos en el sistema. **Entonces:** Se debe permitir, listar, crear los conceptos de costos, deducciones y erogaciones. La información que se debe registrar será la siguiente: • Familia (Categoría principal del concepto) • Concepto (Nombre o descripción del rubro) • Ámbito (Alcance de aplicación) • Territorio (Jurisdicción aplicable) • Base de Cálculo (Parámetro base sobre el cual opera el tributo o erogación) • Tasa % (Porcentaje aplicable) • Fundamento Normativo (Sustento legal) • Vig. Desde y Vig. Hasta (Rango temporal de validez) • Notas (Comentarios adicionales) |

**HU\_003 parametrizar costos transversales por contrato**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **parametrizar y asignar costos transversales** | **Dado que:** Un contrato requiere registrar e imputar costos operativos o administrativos compartidos asociados a un tercero específico. **Cuando:** El contador gestiona las erogaciones o costos transversales del contrato. **Entonces:** Se debe permitir listar, asignar los costos transversales por contrato. La información que se debe registrar y autocompletar será la siguiente: • Identificador de Contrato (ID del contrato afectado) • Entidad (auto) (Institución autocompletada por el sistema según el contrato) • Identificador de Concepto (ID del concepto transversal) • Concepto (auto) (Nombre autocompletado del concepto) • Fecha (Fecha de registro de la erogación) • Valor Sin IVA (Monto monetario de la erogación) • Notas (Observaciones del movimiento) |

**HU\_004 parametrizar subpresupuesto por contrato**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **parametrizar subpresupuesto y estampillas** | **Dado que:** Un contrato requiere distribuir y controlar su techo financiero disponible entre las diferentes gerencias o áreas ejecutoras. **Cuando:**  El contador configure la asignación presupuestal por contrato. **Entonces**: Se debe permitir listar y asignar el subpresupuesto por contrato. La información que se debe registrar y calcular será la siguiente: • Identificador de Contrato (ID del contrato base) • Entidad (auto) (Institución autocompletada por el sistema) • dependencia   (Listado maestro de dependencias creadas para la entidad) • Valor asignado Sin IVA (Techo financiero asignado a la gerencia) • Consumido (auto) (Suma automática de las ejecuciones imputadas) • Saldo (auto) (Diferencia calculada: Valor Asignado \- Consumido) • % de Ejecución (auto) (Porcentaje calculado: Consumido / Valor Asignado \* 100\) |

**HU\_005 parametrizar estampillas por contrato**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **parametrizar subpresupuesto y estampillas** | **Dado que**: Un contrato requiere la liquidación y aplicabilidad de estampillas o tributos territoriales según su lugar de ejecución. **Cuando:**  El contador configure la asignación de estampillas al contrato. **Entonces**: Se debe permitir listar y asignar las estampillas por contrato.  La información que se debe registrar y calcular será la siguiente: • Identificador de Contrato (ID del contrato) • Entidad (auto) (Institución autocompletada) • Identificador de Concepto (ID del tributo o estampilla) • Concepto (auto) (Nombre autocompletado del tributo) • Territorio (auto) (Jurisdicción autocompletada) • Base Cálculo (auto) (Base normativa autocompletada) • Tasa Catálogo % (auto) (Porcentaje base heredado del catálogo) • Override % (opc.) (Tarifa especial o modificación aprobada opcional) • Tasa Aplicable % (auto) (Tasa final resultante: asume el Override % si existe, o la Tasa Catálogo % en caso contrario) • Notas (Observaciones del tributo) |

