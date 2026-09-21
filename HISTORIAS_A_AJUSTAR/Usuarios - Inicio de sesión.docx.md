

| Iniciar sesión |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Iniciar sesión |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Cierre de sesión y expiración |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Usuarios |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Autenticarme en el sistema mediante credenciales para poder gestionar de forma segura los accesos, configuraciones de la plataforma y garantizar la trazabilidad de las acciones. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Solicitar cotización. |  |  |  |

| Situación Actual |
| :---- |
| Actualmente la gestión contractual se maneja mediante del drive en el cual cada carpeta representa a una entidad en específico, en cada carpeta hay un apartado de ejecución donde reposa un excel llamado control de saldos en el cual se encuentra, la oferta económica y cada una de las órdenes de trabajo asociada al contrato en específico. El acceso lo gestiona el administrador del drive pero es simplemente general cada cual puede revisar todos los documentos y/o material contenido, ya sea operativo con las OTs, facturación, licitatorio y demás. |

| Situación Deseada |
| :---- |
| Centralizar la información de todas las entidades para tener una visión unificada y, como primer paso, implementar un portal de acceso seguro donde el usuario deba validar su identidad mediante credenciales obligatorias antes de poder acceder al panel de gestión de accesos, protegiendo así los contratos, ofertas económicas y órdenes de trabajo de accesos no autorizados. |

**HU\_001 Iniciar sesión**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Ingreso exitoso con credenciales válidas** | **Dado que:**  Se encuentra en la pantalla de inicio de sesión de la aplicación. **Cuando:**  Ingresa su correo electrónico y contraseña válidos, y presiona el botón 'Ingresar'. **Entonces:**  Se debe validar las credenciales contra la base de datos, genera el token de sesión y redirige al usuario al panel principal según su rol y permisos asignados. |

**HU\_002 Cierre de sesión y expiración**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Cierre de sesión y expiración** | **Dado que:** El usuario tiene una sesión activa. **Cuando:** Cierra sesión o la sesión expira(por inactividad). **Entonces:** Se invalida la sesión y se redirige a la pantalla de inicio de sesión . Regla de negocio: Si un usuario es eliminado o inactivado, se invalidan todas sus sesiones activas de forma inmediata. |

