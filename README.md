# Seminario .Net - Trabajo final 
## Sistema para la gestión de expedientes

Al finalizar una tarea se debe colocar una `x` entre los corchetes de cada item (checkbox): De `- [ ]` a `- [x]`. Para tener un control qué tareas quedan por completar.

Las secciones que agrupan tareas pueden modificarse, fusionarse u omitirse si se considera necesario durante el proceso de desarrollo. Han sido copiadas directamente desde el enunciado del trabajo.

### Gestión de Usuarios:
- [x] Desarrollar la funcionalidad necesaria para la gestión de usuarios. Cada usuario debe tener nombre, apellido, correo electrónico, contraseña y una lista de permisos.
- [ ] Los usuarios pueden tener múltiples permisos. Sólo el Administrador tendrá los permisos necesarios para listar, dar de baja y modificar cualquier usuario o sus permisos.
- [x] El primer usuario que se registre en el sistema será el Administrador, quien contará con todos los permisos del sistema, incluyendo la capacidad exclusiva para realizar las tareas mencionadas sobre otros usuarios.
- [/] Definir los repositorios y casos de uso que se consideren necesarios.

#### ToDo list para Gestión de Usuarios
  - [x] Crear repositorio de usuarios.
    <!-- - [ ] Crear clase abstracta RepositorioBase. -->
  - [x] Caso de uso alta de un usuario.
    - Desde dónde se hará el alta? => Interfaz
    - Allí se le asignarán los permisos? cuáles? => Ver más abajo
  - [ ] Caso de uso listar usuarios (solo admin).
  - [ ] Caso de uso baja de usuario (solo admin).
  - [ ] Caso de uso modificar usuario (solo admin).

### Persistencia de Datos:
- [ ] En el proyecto SGE.Repositorios, emplear Entity Framework Core para persistir datos en una base de datos SQLite, siguiendo la metodología “code first”.


### Permisos de Usuario:
- [ ] Los usuarios nuevos contarán inicialmente solo con permisos de lectura.
- [ ] Solo el Administrador podrá asignar permisos adicionales.

### Esquema de Permisos:
Mantener el mismo esquema de permisos definido en la primera entrega, con algunas
modificaciones:

- [ ] En esta entrega, se considerará la posibilidad de que un usuario tenga permiso para eliminar expedientes pero no para eliminar trámites individuales. Al eliminar un expediente, todos los trámites asociados se eliminarán automáticamente, incluso si el usuario no tiene el permiso para dar de baja trámites (permiso TramiteBaja).
- [ ] De manera similar, un usuario puede tener permiso para modificar trámites pero no para modificar expedientes. Los cambios automáticos en el estado del expediente al modificar, eliminar o agregar un trámite se realizarán de la misma manera, incluso si el usuario no tiene permisos para modificar expedientes (permiso ExpedienteModificacion).


### Servicio de Autorización:
- [ ] Desarrollar el servicio de autorización ServicioAutorizacion que implemente la interfaz IServicioAutorizacion, reemplazando al servicio de autorización provisorio de la entrega inicial
- [ ] Este servicio debe verificar realmente si el usuario tiene el permiso requerido.

### Interfaz de Usuario:
- [ ] Descartar el proyecto SGE.Consola de la primera entrega.
- [ ] Desarrollar una nueva interfaz de usuario en un proyecto llamado SGE.UI utilizando Blazor. Diseñar libremente esta interfaz de manera que toda la funcionalidad desarrollada en la primera entrega sea accesible desde esta interfaz, agregando la gestión de usuarios requerida.

### Flujo de Gestión:
- [ ] Al iniciar la aplicación, se presentará una pantalla de bienvenida que permitirá a los usuarios iniciar sesión o registrarse.
- [ ] En caso de registro, se proporcionará un formulario para ingresar los datos personales y establecer una contraseña.
- [ ] Los usuarios tendrán la libertad de modificar sus datos personales y contraseña en cualquier momento.
- [ ] Por simplicidad no se implementará ningún mecanismo de recuperación de contraseña. En caso de olvido de contraseña, el usuario deberá contactar al Administrador para restablecerla.
- [ ] Las contraseñas no se almacenarán directamente en la base de datos; en su lugar, se utilizará una función de hash para mayor seguridad.

### Almacenamiento del hash
- [ ] El hash de la contraseña debe almacenarse en la base de datos, nunca la contraseña en sí. Para verificar la identidad del usuario al iniciar sesión, se vuelve a calcular el hash de la contraseña ingresada y se compara con el hash almacenado.
- [ ] Si los hashes coinciden, el usuario ha ingresado la contraseña correcta y se le permite acceder al sistema.

### Acceso Administrativo:
- [ ] El menú de gestión de usuarios será visible exclusivamente para el Administrador tras iniciar sesión con sus credenciales.


