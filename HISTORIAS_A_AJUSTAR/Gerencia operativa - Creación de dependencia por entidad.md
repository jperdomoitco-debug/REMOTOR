

| Creación de dependencias por entidad |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creación de maestra de dependencias |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Gerencia operativa |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  |  |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creación de dependencias por entidad |  |  |  |

| Situación Actual |
| :---- |
| Actualmente, las dependencias de las entidades se manejan de manera fragmentada dentro del archivo Excel de "control de saldos", lo que impide tener una centralización de la información y una trazabilidad adecuada para la gestión de la operación y el presupuesto.  No existe una estructura normalizada en el sistema para definir subdivisiones de entidades basadas en contratos de forma independiente, dificultando el control operativo y la asociación presupuestal. |

| Situación Deseada |
| :---- |
| Se requiere permitir contar con una maestra de dependencias en donde se definan las dependencias asociadas a cada entidad. Centralizar esta información con el fin de poder realizar la configuración adecuada de los presupuestos contractuales y unificar la gestión operativa. |

**HU\_001 Creación de maestra de dependencias**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creación de maestra de dependencias** | **Dado que:**  Las dependencias actualmente se manejan a través de un archivo Excel de control de saldos, lo que impide una centralización y trazabilidad adecuada para definir subdivisiones de entidades y configurar los presupuestos contractuales. **Cuando:**  La gerencia operativa accede a la configuración de dependencias en el sistema. **Entonces:**  Se debe registrar/asociar dependencias a entidades como una tabla maestra centralizada. **Campos requeridos:** Nombre de la dependencia · Entidad asociada · Descripción. |
| **2** | **Modificar dependencia** | **Dado que:**  Una dependencia cambia su nombre, descripción. **Cuando:**  El usuario selecciona "Modificar" y guardar. **Entonces:**  Se actualiza el registro conservando el subpresupuesto asignado y recalculando su saldo. |

