# Prototipo2.1 :computer:


## 1. Crea una nueva versión del prototipo a partir de la disponible en: https://github.com/PyED2018.

  - Hay que tener en cuenta que:
       - El actual prototipo se realizará de manera colaborativa.
       - Será obligatorio el uso y registro en gitHub para gestionar las peticiones de cambio en el 
       repositorio remoto principal del proyecto.
       - Hay que tener en cuenta que el repositorio contiene sólo el código fuente del proyecto.
       No configura ningún proyecto de Eclipse.

## 2. Nuevas clases en el paquete .util

   - <b>Revisar y estudiar las clases</b> Fecha, Criptografia y Formato en el paquete util. 
       - La Clase <b>Fecha</b> contiene un objeto de la clase Calendar de Java para resolver todas las cuestiones del manejo de tiempo. La clase Fecha se completó ya las prácticas anteriores utilizando un adaptador de objeto.
       - La Clase Criptografia contiene métodos estáticos de utilidad para encriptar texto.
       - La Clase Formato contiene métodos estáticos de utilidad relacionados con la validación de formatos de fechas, nif, correo electrónico, complejidad de contraseñas, etc.

## 3. Polimorfismo en el acceso a datos y persistencia en base de datos orientada a objetos

   - Descargar e instalar los ficheros .jar necesarios para poder utilizar la base de datos <b>db4o</b>.
   - Repasar la estructura y la organización de la capa de acceso a datos del proyecto identificando la función de cada una de las clases distribuidas en los distintos subpaquetes que aparecen. Hay que documentar la cabecera de cada una de las clases para indicar claramente su función.
   - Crear un nuevo subpaquete llamado accesoDatos.Db4o para incluir las clases DAO en una versión adecuada que implementa el almacenamiento en base de datos orientada a objetos.
       - Crear una clase llamada <b>Conexion</b>, con patrón Singleton, para albergar la configuración del acceso a la base de datos db4o.
       - En la clase <b>Conexion</b> se configurará la creación de un objeto <b>ObjectContainer</b> conectado a un fichero de base de datos llamado JVDatos.db4o con la configuración embebida por defecto.
   - Crear las correspondientes clases DAO con idénticos nombres a los utilizado en la fachada <b>Datos</b>. Puede hacerse por copia de las ya existentes que resuelven el almacenamiento en ficheros del prototipo anterior.
   - En cada una de las clases DAO se accede al almacenamiento en una base de datos llamada <b>JVdatos.db4o</b>.
       - Comprobar que las cláusulas <b>import</b> de los nuevos DAO son correctas y no se mezclan con otras versiones.
   - Ejecutar opcionalmente el método de carga de datos de prueba desde main(), comprobar que se cargan los datos y desactivar la ejecución del método. Ya se tiene una base de datos válida para pruebas. Ver: DOCUMENTOS DE PROYECTO: diagrama de secuencia del acceso a datos
   - En la clase fachada <b>Datos</b> comprobar que los siguientes métodos utilizan las operaciones UsuariosDAO adecuadas a la versión de acceso a base de datos:
       - Método obtenerUsuario() que recibe un argumento que representa el id del usuario. Devuelve el objeto encontrado o <b>null</b> si no existe.
       - Método obtenerTodosUsuarios() que devuelve una <b>List</b> con los objetos encontrados.
       - Método altaUsuario() recibe un argumento que representa el nuevo usuario. El método DAO lanza una excepción <b>DatosException</b> si ya existe.
       - Método bajaUsuario() recibe un argumento que representa el id del usuario que se quiere borrar. El método DAO lanza una excepción <b>DatosException</b> si el usuario no existe.
       - Método actualizarUsuario() recibe un argumento que representa el usuario con las modificaciones. El método DAO lanza una excepción <b>DatosException</b> si el usuario recibido no existe o no concuerda su id.
       - Método toStringDatosUsuarios() que obtiene, en forma de texto, los datos de todos los usuarios almacenados en el sistema.
       - Método toStringIdUsuarios() que obtiene, en forma de texto, los identificadores de todos los usuarios almacenados en el sistema.
       - Método borrarTodosUsuarios() que quita todos los usuarios almacenados en el sistema.

   - En la clase fachada <b>Datos</b> comprobar que los siguientes métodos utilizan las operaciones <b>SesionesDAO</b> adecuadas a la versión de acceso a base de datos:
       - Método obtenerSesiones() recibe un argumento que representa el idSesion de la sesión. Devuelve el objeto encontrado o <b>null</b> si no existe.
       - Método obtenerTodasSesiones() que devuelve una <b>List</b> con los objetos encontrados.
       - Método altaSesion() recibe un argumento que representa la nueva sesión. El método DAO lanza una excepción <b>DatosException</b> si ya existe.
       - Método bajaSesion() recibe un argumento que representa el idSesion de la sesión que se quiere borrar. El método DAO lanza una excepción <b>DatosException</b> si la sesión no existe.
       - Método actualizarSesion() recibe un argumento que representa la sesión con las modificaciones. El método DAO lanza una excepción <b>DatosException</b> si la sesión recibida no existe o no concuerda su id.
       - Método toStringDatosSesiones() que obtiene, en forma de texto, los datos de todos las sesiones de usuario almacenadas en el sistema.
       - Método toStringIdSesiones() que obtiene, en forma de texto, los identificadores de todas las sesiones almacenadas en el sistema.
       - Método borrarTodosUsuarios() que quita todos las sesiones de usuario almacenadas en el sistema.

   - En la clase fachada <b>Datos</b> comprobar que los siguientes métodos utilizan las operaciones <b>SimulacionesDAO</b> adecuadas a la versión de acceso a base de datos:
       - Método obtenerSimulacion() recibe un argumento que representa el id del usuario y la fecha. Devuelve el objeto encontrado o <b>null</b> si no existe.
       - Método obtenerTodasSimulaciones() que devuelve una <b>List</b> con los objetos encontrados.
       - Método altaSimulacion() recibe un argumento que representa la nueva simulación. El método DAO lanza una excepción <b>DatosException</b> si ya existe.
       - Método bajaSimulacion() recibe un argumento que representa el id del usuario y la fecha de la simulación que se quiere borrar. El método DAO lanza una excepción <b>DatosException</b> si el cliente no existe.
       - Método actualizarSimulacion() recibe un objeto Simulacion con las modificaciones. El método DAO lanza una excepción <b>DatosException</b> si la simulación recibida no existe o no concuerda su id.
       - Método toStringDatosSimulaciones() que obtiene, en forma de texto, los datos de todas las simulaciones almacenadas en el sistema.
       - Método toStringIdUsuarios() que obtiene, en forma de texto, los identificadores de todas las simulaciones almacenadas en el sistema.
       - Método borrarTodasSimulaciones() que quita todas las simulaciones almacenadas en el sistema.

   - En la clase fachada <b>Datos</b> comprobar que los siguientes métodos utilizan las operaciones <b>MundosDAO</b> adecuadas a la versión de acceso a base de datos:
       - Método obtenerMundo() recibe un argumento que representa el id de un mundo. Devuelve el objeto encontrado o <b>null</b> si no existe.
       - Método obtenerTodosMundos() que devuelve una <b>List</b> con los objetos encontrados.
       - Método altaMundo() recibe un argumento que representa el nuevo mundo. El método DAO lanza una excepción <b>DatosException</b> si ya existe.
       - Método bajaMundo() recibe un argumento que representa el id del mundo que se quiere borrar. El método DAO lanza una excepción <b>DatosException</b> si la incidencia no existe.
       - Método actualizarMundo() recibe un objeto Mundo con las modificaciones. El método DAO lanza una excepción <b>DatosException</b> si el mundo recibido no existe o no concuerda su id.
       - Método toStringDatosMundos() que obtiene, en forma de texto, los datos de todos los mundos almacenados en el sistema.
       - Método toStringIdMundos() que obtiene, en forma de texto, los identificadores de todos los mundos almacenados en el sistema.
       - Método borrarTodosMundos() que quita todos los mundos almacenados en el sistema.

## 4. Implementación del inicio de sesión de los usuarios aplicando el patrón MVC sencillo.
Hay que completar los siguientes detalles:

   - Todas las clases de este apartado se localizarán en el en el paquete .accesoUsr
   - En el paquete .accesoUsr, ya está creado el tipo de excepción <b>AccesoUsrExcepction</b> con posibilidad de lanzar excepciones incluyendo un mensaje de texto. Se lanza una excepción de este tipo cuando las credenciales de usuario para el inicio de sesión sean incorrectas.
   - Se deben incorporar dos clases nuevas, en dos nuevos paquetes, llamadas .consola.control<b>.ControlInicioSesion</b> y .consola.vista<b>.VistaInicioSesion</b>.
   - La clase <b>ControlInicioSesion</b>, para el control y verificaciones propias del inicio de sesión, tendrá los siguientes atributos y métodos:
       - Un objeto <b>VistaInicioSesion</b>.
       - Un objeto <b>SesionUsuario</b>.
       - Un objeto <b>Usuario</b>.
       - Un objeto para acceso a datos.
       - Un constructor por defecto.
       - Métodos get...() de acceso que sean necesarios.
       - Un método privado llamado initControlSesion() para inicializar objeto de la propia clase.
       - Un método privado llamado iniciarSesionUsuario() para comprobar las credenciales de usuario y crear la sesión de usuario.
   - La clase <b>VistaInicioSesion</b> implementa la interface OperacionesVistaSesion con los métodos:
       - Método mostrarMensaje(String mensaje)  -heredado de <b>OperacionesVista</b>- que muestra en el interfaz de usuario el texto recibido como parámetro.
       - Método para pedir idUsr de usuario pedirIdUsr().
       - Método para pedir claveAceso de usuario pedirClaveAcceso().
   - La clase <b>VistaInicioSesion</b> tendrá los siguientes atributos:
       - Un objeto para la entrada por consola-teclado.
       - Un constructor que inicializa el atributo.
   - De manera normal el sistema debe <b>pedir el idUsr y la claveAcceso</b> de usuario que serán verificadas respectivamente.
   - Después se debe <b>dar paso a la sesión de usuario</b> efectiva cambiando el estado de la sesión a ACTIVA en el atributo correspondiente en el objeto SesionUsuario recién iniciada. 
   - Será posible <b>introducir el idUsr directamente en la línea de comandos</b> a la hora de ejecutar la aplicación. En ese caso, directamente, se pedirá la claveAcceso y se verificarán las credenciales.
   - Una vez iniciada la sesion válida; se pasa el control a un objeto de la clase <b>ControlSimulacion</b>, que apoyandose en una clase <b>VistaSimulacion</b> y  los objetos necesarios del modelo, lanza una demo del Juego de la Vida, tal como ya se ejecutaba en los prototipos de versiones anteriores.
   - La clase <b>ControlSimulacion</b> tendrá los atributos y métodos:
       - Un objeto <b>VistaSimulacion</b>.
       - Un objeto <b>Simulacion</b>.
       - Un objeto <b>Mundo</b>.
       - Un objeto para acceso a datos.
       - Métodos get...() de acceso que sean necesarios.
       - Un método privado llamado initControlSimulacion() para inicializar objeto de la propia clase.
       - Un método privado llamado arrancarSimulacion() para poner en marcha una simulación con datos almacenados previamente.
   - La clase <b>VistaSimulacion</b> implementa la interface OperacionesVista con un único método: mostrarMensaje(String mensaje) que muestra en el interfaz de usuario el texto recibido como parámetro.
   - La clase VistaSimulacion tendrá además los siguientes atributos y métodos:
       - Un objeto para la entrada por teclado.
       - Un constructor que inicializa el atributo.
       - Un método mostrarMundo().

## 5. Aplicación del patrón MVC para crear el menú principal de la aplicación

- En el subpaquete accesoUsr.consola, crear la clase <b>VistaPrincipal</b> que se encargará de mostrar un menú simple de 
  texto y de la interacción de usuario; para ello dispondrá de:
  
     - Un atributo privado para mantener la opción activala del menú.
     - Los métodos de la interface <b>OperacionesVista</b> que debe implementar.
     - Un método mostrar() que simplemente despliega el menú.
     - Un método pedirOpcion() que actualiza y devuelve la opción activa.

- En el subpaquete accesoUsr.control, crear la clase ControlPrincipal con las siguientes características:
     - Tiene un atributo privado de la clase modelo.SesionUsuario.
     - Tiene un atributo privado llamado vistaPrincipal de la clase <b>VistaPrincipal</b>.
     - Dispondrá de un constructor convencional que recibirá un identificador de usuario, que en un momento dado 
     puede ser <b>null</b>. 
     - Dispondrá de un método privado para procesar la opción de menú procesarOpcion(int opcion).
     - Dispondrá de métodos privados para resolver las operaciones de cada opción de menú:
         - altaUsuario()
         - modificacionesUsuario()
         - bajaUsuario()
         - listarUsuarios()
         - .....
         - .....
 - Desde el constructor de esta clase se lanzará un método privado llamado secuenciaPrincipal(),
  que en un bucle continuo: 
    - Mostrará el menú principal accediendo a vistaPrincipal.
    - Pedirá una opción accediendo a vistaPrincipal.
    - Procesará la opción de menú.
