

| Asignar permisos a rol |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Asignar permisos a rol |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Configurar las reglas detalladas (qué módulos ver y qué acciones realizar) que regirán el comportamiento de un rol específico dentro del sistema. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Asignar permisos a rol |  |  |  |

| Situación Actual |
| :---- |
| Cualquier persona puede revisar, y potencialmente alterar o eliminar, todos los documentos críticos vulnerando la integridad de los datos. |

| Situación Deseada |
| :---- |
| Mapear cada rol creado con los módulos específicos del sistema (Ej. almacenista, recepción, coordinador administrativo) y habilitar /deshabilitar acciones CRUD (Crear, Leer, Actualizar, Borrar) de manera totalmente independiente. |

**HU\_001 Asignar permisos a rol**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Asignar permisos a rol** | **Dado que:** El administrador de acceso selecciona un rol específico y accede a la vista de la matriz de permisos. **Cuando**: Marca o desmarca de forma granular los permisos por componente o sección y guarda los cambios. **Entonces:**  El sistema persiste estas reglas de control de acceso para el rol. En consecuencia, cualquier usuario asociado a dicho rol obtendrá exclusivamente las autorizaciones configuradas, permitiéndole interactuar solo con las acciones permitidas mientras que las secciones sin acceso permanecerán ocultas e inaccesibles. |

