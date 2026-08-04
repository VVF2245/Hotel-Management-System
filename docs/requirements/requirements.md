# Requisitos

## Requisitos de información

### RI-01. Información de usuarios

**Como propietario del hotel**, quiero almacenar la información de los usuarios del sistema (nombre y apellidos, nombre de usuario, correo electrónico, contraseña cifrada, rol asignado —recepción, limpieza o administración—, estado de la cuenta y fecha de creación), para identificar a cada trabajador, autenticar su acceso y controlar los permisos según su función.

### RI-02. Información de habitaciones

**Como propietario del hotel**, quiero almacenar la información de las habitaciones (número de habitación, tipo de habitación, precio por noche, estado —libre, ocupada o en limpieza— y observaciones si fueran necesarias), para conocer en todo momento las características y disponibilidad de cada habitación.

### RI-03. Información de clientes

**Como propietario del hotel**, quiero almacenar la información de los clientes (nombre y apellidos, documento de identidad, teléfono y correo electrónico), para identificar correctamente a las personas que realizan reservas y facilitar la comunicación con ellas.

### RI-04. Información de reservas

**Como propietario del hotel**, quiero almacenar la información de las reservas (cliente asociado, habitación asignada, fecha de entrada, fecha de salida, estado de la reserva, fecha de creación y usuario que realizó la reserva), para gestionar las estancias del hotel y evitar solapamientos entre reservas.

### RI-05. Historial de reservas

**Como propietario del hotel**, quiero almacenar el historial de las reservas (tipo de acción realizada, usuario que realizó la acción, fecha y hora de la acción y motivo de la cancelación cuando exista), para mantener un registro de auditoría sobre todas las modificaciones y cancelaciones realizadas.

### RI-06. Información de tareas de limpieza

**Como propietario del hotel**, quiero almacenar la información de las tareas de limpieza (habitación asociada, estado de la tarea, empleado de limpieza asignado, fecha y hora de inicio, fecha y hora de finalización y observaciones o incidencias), para controlar el proceso de limpieza y conocer cuándo una habitación vuelve a estar disponible.

### RI-07. Información del estado de las habitaciones

**Como propietario del hotel**, quiero almacenar el estado actual y el historial de cambios de estado de cada habitación (estado anterior, estado nuevo, fecha y hora del cambio y usuario o proceso que realizó la modificación), para conocer la trazabilidad de la ocupación y las tareas de limpieza.

### RI-08. Información para el panel de control

**Como propietario del hotel**, quiero disponer de la información necesaria para el panel de control (número de habitaciones libres, ocupadas y en limpieza, porcentaje de ocupación y número de reservas activas), para obtener una visión general del funcionamiento del hotel y facilitar la toma de decisiones.

### RI-09. Información de configuración del hotel

**Como propietario del hotel**, quiero almacenar la información general del hotel (nombre del hotel, número total de habitaciones y configuración básica del sistema), para personalizar el funcionamiento de la aplicación y facilitar futuras ampliaciones.

## Requisitos funcionales

### RF-01. Autenticación de usuarios

**Como trabajador del hotel**, quiero iniciar sesión con mi usuario y contraseña, para acceder al sistema de forma segura según mi rol.

### RF-02. Gestión de usuarios

**Como administrador del sistema**, quiero crear, modificar, desactivar y eliminar usuarios, para gestionar el acceso de los trabajadores a la aplicación.

### RF-03. Asignación de roles

**Como administrador del sistema**, quiero asignar el rol de recepción, limpieza o administración a cada usuario, para controlar los permisos de acceso a las distintas funcionalidades.

### RF-04. Gestión de habitaciones

**Como administrador del sistema**, quiero registrar, modificar y eliminar habitaciones, para mantener actualizada la información del hotel.

### RF-05. Consulta de habitaciones

**Como trabajador del hotel**, quiero consultar el listado de habitaciones y su estado, para conocer su disponibilidad en cualquier momento.

### RF-06. Creación de reservas

**Como recepcionista**, quiero registrar nuevas reservas indicando el cliente, la habitación y las fechas de estancia, para organizar las ocupaciones del hotel.

### RF-07. Validación de disponibilidad

**Como recepcionista**, quiero que el sistema compruebe automáticamente la disponibilidad de una habitación antes de confirmar una reserva, para evitar solapamientos entre reservas.

### RF-08. Modificación de reservas

**Como recepcionista**, quiero modificar una reserva existente, para actualizar los datos cuando sea necesario.

### RF-09. Cancelación de reservas

**Como recepcionista**, quiero cancelar una reserva, para liberar la habitación y dejar constancia de la cancelación en el historial.

### RF-10. Registro del historial

**Como administrador del sistema**, quiero que el sistema registre todas las acciones realizadas sobre las reservas, para disponer de una trazabilidad completa de los cambios.

### RF-11. Registro de clientes

**Como recepcionista**, quiero registrar los datos de los clientes, para asociarlos correctamente a sus reservas.

### RF-12. Check-in

**Como recepcionista**, quiero registrar el check-in de un cliente, para indicar que ha comenzado su estancia y actualizar automáticamente el estado de la habitación a "ocupada".

### RF-13. Check-out

**Como recepcionista**, quiero registrar el check-out de un cliente, para finalizar su estancia y cambiar automáticamente el estado de la habitación a "en limpieza".

### RF-14. Consulta de habitaciones pendientes de limpieza

**Como personal de limpieza**, quiero visualizar las habitaciones que requieren limpieza, para organizar mi trabajo diario.

### RF-15. Finalización de tareas de limpieza

**Como personal de limpieza**, quiero marcar una habitación como limpia cuando termine la tarea, para que vuelva a estar disponible.

### RF-16. Registro de incidencias de limpieza

**Como personal de limpieza**, quiero añadir observaciones o incidencias durante la limpieza, para informar de cualquier problema detectado.

### RF-17. Actualización del estado de las habitaciones

**Como sistema**, quiero actualizar automáticamente el estado de las habitaciones en función de los eventos de check-in, check-out y finalización de la limpieza, para mantener la información siempre actualizada.

### RF-18. Panel de control

**Como administrador del sistema**, quiero visualizar un panel de control con indicadores de ocupación y estado de las habitaciones, para conocer la situación general del hotel.

### RF-19. Consulta de reservas

**Como recepcionista**, quiero consultar las reservas existentes mediante filtros como cliente, habitación o fechas, para localizar rápidamente la información necesaria.

### RF-20. Control de acceso

**Como administrador del sistema**, quiero restringir el acceso a las funcionalidades según el rol del usuario, para garantizar la seguridad y la correcta gestión de la aplicación.


## Requisitos no funcionales

### RNF-01. Seguridad de autenticación

**Como propietario del hotel**, quiero que el sistema requiera autenticación mediante usuario y contraseña antes de permitir el acceso, para evitar que personas no autorizadas puedan consultar o modificar información del hotel.

### RNF-02. Control de acceso por roles

**Como propietario del hotel**, quiero que cada usuario tenga permisos limitados según su rol (recepción, limpieza o administración), para garantizar que cada trabajador solo pueda acceder y modificar la información necesaria para sus funciones.

### RNF-03. Facilidad de uso

**Como propietario del hotel**, quiero que la aplicación tenga una interfaz sencilla e intuitiva, para que los trabajadores puedan utilizarla sin necesidad de una formación técnica avanzada.

### RNF-04. Capacidad de ampliación

**Como propietario del hotel**, quiero que el sistema pueda incorporar nuevas funcionalidades en el futuro, como reservas online para clientes, para permitir el crecimiento de la aplicación sin rehacer el sistema completo.

## Reglas de negocio

### RN-01. Asignación única de habitaciones

Una habitación no podrá tener más de una reserva activa para el mismo periodo de fechas, evitando que dos clientes puedan ocupar la misma habitación simultáneamente.

### RN-02. Control de disponibilidad de habitaciones

Una habitación solo podrá asignarse a una reserva si se encuentra disponible durante todas las fechas indicadas de la estancia.

### RN-03. Gestión de estados de habitaciones

Una habitación solo podrá tener uno de los siguientes estados: libre, ocupada o en limpieza.

### RN-04. Cambio automático de estado por check-in

Cuando un cliente realice el check-in, la habitación asociada a su reserva deberá cambiar automáticamente al estado "ocupada".

### RN-05. Cambio automático de estado por check-out

Cuando un cliente realice el check-out, la habitación asociada deberá cambiar automáticamente al estado "en limpieza".

### RN-06. Disponibilidad tras limpieza

Una habitación que se encuentre en estado "en limpieza" no podrá asignarse a una nueva reserva hasta que el personal de limpieza confirme que la tarea ha finalizado y la habitación pase al estado "libre".

### RN-07. Cancelación de reservas

Cuando una reserva sea cancelada, la habitación asociada quedará disponible para futuras reservas siempre que no existan otras restricciones.

### RN-08. Registro obligatorio de cancelaciones

Toda cancelación de una reserva deberá registrar el usuario que la realizó, la fecha y hora de la acción y la reserva afectada.

### RN-09. Gestión de permisos según rol

Los usuarios solo podrán realizar las acciones permitidas para su rol:

* Recepción podrá gestionar clientes, reservas, check-in y check-out.
* Limpieza podrá consultar habitaciones pendientes de limpieza, finalizar tareas y añadir observaciones.
* Administración tendrá acceso completo al sistema.

### RN-10. Creación de reservas con datos obligatorios

Toda reserva deberá estar asociada a un cliente, una habitación, una fecha de entrada y una fecha de salida antes de poder ser confirmada.

### RN-11. Fechas válidas de estancia

La fecha de salida de una reserva deberá ser posterior a la fecha de entrada.
