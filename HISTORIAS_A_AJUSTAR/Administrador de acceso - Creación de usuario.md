

| Creacion de usuario |
| :---: |

| Clasificación: |  | Historia de Usuario |  |  |  | X | Control de cambios |  |  |  |  |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Control de cambios a:** |  |  |  |  |  |  |  |  |  |  |  |
| **Historia de usuario:** |  |  |  |  |  |  |  |  |  |  |  |
| HU\_001 |  | Creacion de usuario |  |  |  |  |  |  |  |  |  |
| HU\_002 |  | Generación de credenciales iniciales |  |  |  |  |  |  |  |  |  |
| **Rol (es) “Yo como”** |  | Administrador de acceso |  |  |  |  |  |  |  |  |  |
| **Funcionalidad “Quiero”** |  | Registrar nuevos usuarios en el sistema, capturando su información laboral básica para permitirles el ingreso trazable a la plataforma. |  |  |  |  |  |  |  |  |  |
| **Prioridad** |  | Alta |  | Media |  | x | Baja |  |  | **Módulo / Aplicación** | Control de acceso |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
| **Versión** | **Fecha** | **Autor** |  |  | **Usuario solicitante** |  |  | **Descripción** |  |  |  |
| 1.0 | 04-07-2026 | Julián Perdomo |  |  | Luis Miguel Gonzáles |  |  | Creacion de usuario |  |  |  |

| Situación Actual |
| :---- |
| Actualmente el acceso se da compartiendo un enlace general de Google Drive sin un directorio que diferencie un colaborador de otro. |

| Situación Deseada |
| :---- |
| Tener un formulario estandarizado donde el administrador de acceso pueda dar de alta a nuevos usuarios especificando sus datos personales, correo corporativo y generación de credenciales iniciales. |

**HU\_001 Creacion de usuario**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Creacion de usuario** | **Dado que**: El Administrador de acceso está en el módulo de gestión de usuarios y selecciona crear usuario. **Cuando**: Completa todos los campos obligatorios del formulario validando el formato de correo y guarda los cambios. **Entonces**: Se debe inserta el registro del usuario en la base de datos y le asigna el estado activo.  El formulario debe contener como mínimo: Nombres completos Apellidos completos Correo electrónico Número de documento Cargo o Área |

**HU\_002 Generación de credenciales iniciales**

| \# | Contexto | Criterios de Aceptación – Resultado / Comportamiento esperado |
| :---- | :---- | :---- |
| **1** | **Generación de credenciales iniciales** | **Dado que:** Se crea un usuario exitosamente. **Cuando:** Se confirma el registro. **Entonces:** El sistema genera una contraseña temporal y la envía al correo ingresado, solicitando cambio en el primer inicio de sesión. |

