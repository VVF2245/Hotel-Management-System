# Interview with client

**Client**: Hello, thank you for taking the time to speak with me. I’ll explain what I need. I run a small hotel with around 40 rooms, and right now we manage everything using paper, phone calls, and Excel… and it’s becoming a mess.

**Analyst**: Perfect, could you tell me how you are currently managing it and what the main issues are?

**Client**: The main issue is that bookings sometimes overlap. Someone writes down a room for certain dates, but then another person might book the same room without realizing it. We also don’t always know which rooms are clean and ready to be used again.

**Analyst**: I understand. So there are two main problems: preventing booking overlaps and managing room status. Who is currently using the system inside the hotel?

**Client**: We have three types of staff: reception, cleaning, and administration. Each one does their part, but there is no shared system, everyone works independently.

**Analyst**: Understood. That means the system will need user roles and control over what each role can see and modify. In reception, I assume they handle bookings, correct?

**Client**: Yes, reception is responsible for bookings, customer service, check-ins and check-outs. They record the guest name, dates, and assigned room.

**Analyst**: How is room availability defined? For example, if someone books from the 10th to the 12th, is the room occupied for all those days?

**Client**: Yes, it is based on full days. If someone checks in on the 10th, that room cannot be assigned to anyone else on that day.

**Analyst**: Understood. What happens when a booking is cancelled?

**Client**: The booking is removed and the room becomes available again. However, we would like to keep a record of who cancelled it and when.

**Analyst**: Perfect, that implies keeping a history of booking actions. Regarding the rooms, what information do you store for each one?

**Client**: Each room has a number, a type (single, double, suite), a price per night, and a status.

**Analyst**: What values can that status have?

**Client**: It can be available, occupied, or in cleaning.

**Analyst**: Is that status updated manually or would you like part of it to be automated?

**Client**: Right now it’s manual, but we would like some automation. For example, when a guest checks in, the room should automatically become occupied, and when they check out, it should go to cleaning.

**Analyst**: Understood, that implies event-driven status updates. Regarding the cleaning staff, what exactly do they need?

**Client**: They need to see which rooms are in cleaning, mark when they finish a room, and add notes, for example if something is missing or there is a problem.

**Analyst**: Is cleaning always done after check-out, or can it happen at other times?

**Client**: Normally after check-out, but sometimes also during a stay if there is a request or an issue.

**Analyst**: Understood. So cleaning can be triggered by scheduled events as well as incidents. Regarding administration, what are their responsibilities?

**Client**: Administration has full control of the system: managing users, rooms, bookings, and overall hotel configuration.

**Analyst**: Perfect, so administration acts as a full-access role with permissions over the entire system.

**Client**: Yes, exactly.

**Analyst**: Besides that, would you like any kind of global overview of the hotel?

**Client**: Yes, we would like a general dashboard showing how many rooms are available, how many are occupied, and the overall occupancy rate.

**Analyst**: Understood, that would be a management dashboard with key metrics.

**Client**: Yes, something visual and easy to understand.

**Analyst**: Got it. Will the system be used only internally, or will guests be able to book rooms directly in the future?

**Client**: For now only internally. In the future we might allow online bookings, but it is not required at the moment.

**Analyst**: Perfect, but we will design it in a way that allows future expansion without major changes. Will every employee have their own user account?

**Client**: Yes, each employee should have their own login. Not everyone should be able to do everything.

**Analyst**: Understood. So we need role-based access control: reception, cleaning, and administration, each with different permissions. Administration will have full access, reception will manage bookings, and cleaning will manage room status.

**Client**: Yes, that is correct.

**Analyst**: Perfect. To confirm, I will summarize what I have understood:

The system must manage rooms with number, type, price, and status. The status can be available, occupied, or in cleaning, with automatic updates based on events such as check-in and check-out.

Bookings will include guest name, check-in and check-out dates, and assigned room, preventing date overlaps. A history of booking actions, including cancellations, must be stored.

There will be user roles: reception, cleaning, and administration, with administration having full access to the system.

The cleaning module will allow staff to view rooms pending cleaning, mark them as completed, and add notes.

A dashboard will provide occupancy metrics and general hotel overview.

The system should allow future expansion to support external online bookings.

**Client**: Yes, that is all correct.

**Analyst**: Perfect, with this we can define the use cases and the system model to start the design.



# Entrevista con cliente

**Cliente**: Hola, gracias por atenderme. Te explico un poco lo que necesito. Tengo un hotel pequeño de unas 40 habitaciones y ahora mismo lo gestionamos todo con papel, llamadas y Excel… y empieza a ser un caos.

**Analista**: Perfecto, cuénteme cómo lo están gestionando ahora y cuáles son los principales problemas que están teniendo.

**Cliente**: El principal problema es que las reservas a veces se pisan. Alguien apunta una habitación para unas fechas, pero luego otra persona puede reservar la misma sin darse cuenta. También pasa que no sabemos con seguridad qué habitaciones están limpias o listas para volver a usarse.

**Analista**: Entiendo. Entonces hay dos problemas principales: control de reservas sin solapamientos y gestión del estado de las habitaciones. ¿Quiénes utilizan actualmente el sistema dentro del hotel?

**Cliente**: Somos tres tipos de trabajadores: recepción, limpieza y administración. Cada uno hace su parte, pero no tenemos un sistema común, cada uno trabaja por su cuenta.

**Analista**: Entendido. Eso implica que el sistema deberá diferenciar roles de usuario y controlar qué información puede ver o modificar cada uno. En recepción imagino que gestionan reservas, ¿correcto?

**Cliente**: Sí, recepción se encarga de las reservas. Atención al cliente, entradas y salidas. Ellos apuntan el nombre del cliente, fechas y la habitación asignada.

**Analista**: ¿Cómo se define la disponibilidad de una habitación? Por ejemplo, si alguien reserva del día 10 al 12, ¿la habitación está ocupada esos días completos?

**Client**: Sí, son días completos. Si alguien entra el día 10, esa habitación ya no se puede asignar a otra persona ese día.

**Analista**: Entendido. ¿Y qué ocurre cuando un cliente cancela una reserva?

**Cliente**: Se elimina la reserva y la habitación vuelve a estar disponible. Pero nos gustaría que quedara registrado quién hizo la cancelación y cuándo.

**Analista**: Perfecto, eso implica mantener un historial de acciones sobre las reservas. Ahora, sobre las habitaciones, ¿qué información manejan de cada una?

**Cliente**: De cada habitación tenemos el número, el tipo (individual, doble, suite), el precio por noche y el estado.

**Analista**: ¿Qué valores puede tener ese estado?

**Cliente**: Puede estar libre, ocupada o en limpieza.

**Analista**: ¿Ese estado se cambia manualmente o les gustaría que parte del proceso fuera automático?

**Cliente**: Ahora lo hacemos manual, pero nos gustaría que algunas cosas fueran automáticas. Por ejemplo, cuando un cliente hace check-in la habitación debería pasar a ocupada, y cuando hace check-out debería pasar a limpieza.

**Analista**: Entendido, eso implica automatización de estados basada en eventos del sistema. En cuanto al equipo de limpieza, ¿qué necesidades tienen exactamente?

**Cliente**: Ellos necesitan ver qué habitaciones están en limpieza, marcar cuando terminan una habitación y poder añadir notas, por ejemplo si falta algo o si hay algún problema.

**Analista**: ¿La limpieza siempre se hace después del check-out o puede ocurrir en otros momentos?

**Cliente**: Normalmente después del check-out, pero a veces también durante la estancia si hay algún problema o solicitud.

**Analista**: Entendido. Entonces la limpieza puede generarse tanto por eventos programados como por incidencias. Sobre la administración, ¿qué funciones tiene?

**Cliente**: La administración debe tener control total del sistema. Gestión de usuarios, habitaciones, reservas y configuración general del hotel.

**Analista**: Perfecto, entonces administración actúa como rol con acceso completo y permisos sobre toda la aplicación.

**Cliente**: Sí, exactamente así.

**Analista**: Además de esto, ¿les gustaría tener algún tipo de información global del hotel?

**Cliente**: Sí, nos gustaría ver un resumen general. Por ejemplo cuántas habitaciones están libres, cuántas ocupadas y cuánta ocupación tenemos en total.

**Analista**: Entendido, eso sería un panel de control con métricas de ocupación.

**Cliente**: Sí, algo visual y sencillo de entender.

**Analista**: Entendido. ¿El sistema lo usarán solo internamente o también los clientes podrán reservar directamente en el futuro?

**Cliente**: De momento solo internamente. En el futuro quizá permitamos reservas desde internet, pero ahora no es necesario.

**Analista**: Perfecto, pero lo tendremos en cuenta para que el sistema pueda crecer en esa dirección sin rehacerlo. ¿Todos los trabajadores tendrán acceso al sistema con usuario propio?

**Cliente**: Sí, cada trabajador debería tener su usuario. No todo el mundo debe poder hacer lo mismo.

**Analista**: Entendido. Entonces necesitamos control de acceso por roles: recepción, limpieza y administración, con permisos diferenciados. Administración tendrá acceso completo, recepción gestionará reservas y limpieza gestionará el estado de habitaciones.

**Cliente**: Sí, correcto.

**Analista**: Perfecto. Para confirmar, resumo lo entendido:

El sistema deberá gestionar habitaciones con información de número, tipo, precio y estado. El estado puede ser libre, ocupada o en limpieza, con cambios automáticos basados en eventos como check-in y check-out.

Se gestionarán reservas con nombre de cliente, fechas de entrada y salida y habitación asignada, evitando solapamientos de fechas. Se deberá mantener un historial de cambios, incluyendo cancelaciones.

Habrá usuarios con roles diferenciados: recepción, limpieza y administración, siendo administración el rol con acceso completo al sistema.

El sistema de limpieza permitirá ver habitaciones pendientes de limpieza, marcar tareas como completadas y añadir observaciones.

Se incluirá un panel de control con métricas de ocupación del hotel.

El sistema deberá permitir crecimiento futuro hacia reservas externas desde internet.

**Cliente**: Sí, todo eso es correcto.

**Analista**: Perfecto, con esto podemos definir los casos de uso y el modelo del sistema para empezar el diseño.
