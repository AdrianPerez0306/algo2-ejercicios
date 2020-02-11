
## Reserva de libros

### Punto a) Contexto

Dentro de la construcción de una aplicación para la administración de la biblioteca de una facultad hay que diseñar parte del manejo de reservas y préstamos de libros. Hay que manejar que de cada libro puede haber uno o varios ejemplares.

La biblioteca permite a sus usuarios registrados reservar libros entre determinadas fechas, p.ej. hoy 4/12 un usuario puede reservar El Quijote entre el 15/12 y el 30/12.

El día en que comienza la reserva (en el ejemplo, el 15/12) el usuario puede ir a buscar el libro que reservó. Si el usuario no retira el libro ni ese día ni el siguiente, entonces la reserva queda sin efecto.

En el momento de retirar, el usuario puede cambiar la fecha de devolución. Los usuarios también pueden retirar libros sin reserva previa.

La aplicación debe cuidar que no se reserve o preste un ejemplar no disponible. Un ejemplar reservado se considera no disponible.

Respecto del tiempo que se puede reservar/prestar un libro, la biblioteca maneja tres categorías:

- **Críticos**: se le pueden prestar 5 días a los docentes, 2 días al resto de los usuarios. 
- **Normales**: se le pueden prestar 10 días a cualquier usuario. 
- **Masivos**: se pueden prestar 20 días a cualquier usuario. 

Cuando se registra cada libro, quien lo registra indica a qué categoría pertenece; después un operador puede cambiar la categoría de un libro en cualquier momento.

Diseñar la parte de la aplicación que responde a estos requerimientos:

- dados un libro y una fecha (hoy o una fecha del futuro), saber cuántos ejemplares están reservados para esa fecha, cuántos están/estarán prestados (considerar que el libro volverá a la biblioteca la fecha indicada para su devolución) y cuántos están/estarán disponibles. 
- dados un libro, un usuario y dos fechas, registrar una reserva. Hay que controlar que haya algún ejemplar disponible durante todo el período de la reserva y que la cantidad de días no supere lo que corresponde a la categoría del libro, y eventualmente al usuario. 
- dado un libro, un usuario y una fecha, registrar un préstamo sin reserva previa que empieza "hoy" y termina en la fecha indicada. Mismos controles que para la reserva. 
- dada una reserva y una fecha, registrar que el usuario retiró el libro reservado, en donde la fecha real de devolución es la indicada. Mismos controles que para la reserva, si la fecha indicada es posterior a la original de la reserva. 

De la búsqueda de los objetos de negocio (p.ej. el que representa un libro) se encargarán otros componentes que no son los que deben diseñar ustedes, a ustedes les llegan los objetos ya buscados y encontrados. Esto implica que no se tienen que preocupar por nada de la UI, y tampoco por traducir los datos ingresados por el usuario en objetos, a ustedes les van a llegar los objetos (instancias de las clases que ustedes deben definir) listos para enviarle mensajes.

Tampoco hay que preocuparse por la persistencia, supongan que todos los objetos necesarios pueden vivir en memoria, y que cada tanto hay un botón que plancha el estado de la máquina virtual a disco para recovery. No es necesario tener un repositorio central (p.ej. un objeto que conozca a todas las reservas), armen los objetos que necesiten para lo que se pide en el enunciado.

### Punto b)

Cuando un usuario retira un libro, hay que avisarle al depósito que lo vaya a buscar. Para eso hay un singleton Depósito que entiende un mensaje

```java
buscarLibro(String isbn)
```

donde el ISBN es un código que identifica unívocamente a un libro en el universo.

Agregar al diseño una forma de avisarle al depósito, de forma tal que en lo que se hizo en el punto a) no haya referencias al depósito.

### Punto c) Notificaciones a los socios

El día antes de que un usuario debe devolver un libro, hay que enviarle un mensaje al usuario. Para eso hay definido un Avisador que entiende un mensaje

```java
avisarProximaDevolucion(Collection prestamos)
```

donde cada elemento de prestamos representa un préstamo, y va a ser un objeto de los definidos por uds. en el ítem a), del cual alguien (no ustedes) ya determinó que corresponde avisar. Implementar el método `avisarProximaDevolucion(Collection prestamos)`, teniendo en cuenta que existen tres canales de envío de mensajes:

- Por mail, para lo cual hay un singleton MailSender que entiende un mensaje `sendMail(String direccion, String asunto, String texto)`. 
- Por celular, para lo cual hay un singleton PhoneTextSender que entiende un mensaje `sendMessage(String telefono, String texto)`. 
- Por mensaje grabado, para lo cual hay un singleton PhoneVoiceSender que entiende un mensaje `sendMessage(String telefono, String texto)`. 

Al registrar cada usuario, se indica por cuál/es (puede ser más de uno) de estos medios se le enviarán los mensajes. Después esta información se puede cambiar. Todo esto no lo deben hacer ustedes, lo que deben hacer es modelar la información para que el Avisador pueda enviarle mensajes a los usuarios.

El mensaje es "Mañana debe devolver el libro " + nombre del libro + “ a la biblioteca", en el caso del mail el asunto es "Aviso de la biblioteca".

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Subastas on-line](subastas.md)
