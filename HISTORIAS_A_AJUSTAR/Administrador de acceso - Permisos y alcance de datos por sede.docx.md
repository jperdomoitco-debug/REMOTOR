

| Permisos y alcance de datos por sede |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Configurar el alcance por sede |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Configurar que cada sucursal o satélite visualice únicamente sus órdenes de trabajo, mientras la gerencia o administración consulta el consolidado global. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Configuración del alcance de datos por sede. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente el acceso a los datos que es un Excel,  no diferencia sucursales por lo que todos los usuarios ven la información completa, sin importar la sede. |

| Situación Deseada |
| :---- |
| Se desea configurar el alcance por sede: cada sucursal o satélite ve únicamente sus órdenes de trabajo y la gerencia o administración consulta el consolidado global. |

**HU\_001 Configurar el alcance por sede**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Configurar el alcance por sede** | **Dado que:** el sistema opera en varias sedes **Cuando:** el administrador configura el alcance de datos de un rol por sede **Entonces:** el rol solo visualiza las órdenes de trabajo de su sucursal o satélite; la gerencia o administración consulta el global. Regla de negocio: Los permisos de datos son por sede, es decir cada sucursal o satélite visualiza únicamente sus órdenes de trabajo. |

