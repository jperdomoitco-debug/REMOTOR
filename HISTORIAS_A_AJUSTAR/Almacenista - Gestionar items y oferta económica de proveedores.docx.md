

| Gestionar items y oferta económica de proveedores |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Crear ítems y actualizar ítems |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Crear y actualizar ofertas de proveedores |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Almacenista |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Centralizar la información de artículos, servicios y proveedores en un único catálogo maestro para eliminar la dispersión de datos y los procesos manuales, permitiendo consultar y gestionar ofertas de manera dinámica, facilitando decisiones de compra eficientes y evitando el retrabajo operativo. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Compras |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Gestionar items y oferta económica de proveedores |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, no existe una fuente única de verdad para los artículos y servicios. La información reside en archivos dispersos, correos electrónicos y hojas de cálculo, lo que genera una dependencia del conocimiento informal. Esto provoca procesos manuales redundantes, dificultades para identificar quién suministra qué, y un alto riesgo de errores al tomar decisiones de compra por falta de datos estructurados. |

| Situación Deseada |
| :---- |
| Crear un Catálogo Maestro de artículos y servicios centralizado, donde la definición técnica de un ítem sea independiente de sus proveedores. El sistema permitirá vincular dinámicamente múltiples proveedores a un ítem, garantizando que la información esté siempre disponible, actualizada y accesible para tomar decisiones de abastecimiento rápidas, reduciendo drásticamente el tiempo operativo y los retrabajos. |

**HU\_001 Crear ítems**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Crear ítem** | **Dado que:** Se necesita registrar un artículo nuevo **Cuando:** Se ingrese la información técnica (nombre, descripción, unidad) **Entonces:** El sistema creará el registro sin exigir proveedores. |
| **2** | **Corregir especificaciones** | **Dado que:** El ítem existe **Cuando:** Necesite corregir una especificación **Entonces:** El sistema permitirá el cambio sin afectar ofertas vinculadas. |
| **3** | **Evitar duplicados** | **Dado que:** intento crear un ítem **Cuando:** detecte un nombre similar **Entonces:** el sistema mostrará una alerta para evitar duplicados. |

**HU\_002 Crear y actualizar ofertas de proveedores**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Agregar oferta** | **Dado que:** tengo un ítem **Cuando:** presione "Agregar oferta" **Entonces:** el sistema solicitará solo 3 datos: Proveedor, Precio actual y Tiempo de entrega. |
| **2** | **Editar oferta** | **Dado que:** las condiciones cambian **Cuando:** edite una oferta **Entonces:** el sistema guardará el dato nuevo para mantener la información vigente. |

