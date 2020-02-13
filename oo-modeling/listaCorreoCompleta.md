
## Listas de Correo

Se requiere un software que maneje listas de correo. El sistema debe contemplar: 

### Envío de correo

Enviar un correo, recibiendo la dirección de e-mail origen del correo, título y texto. El envío de correos a la lista puede definirse como abierto (cualquiera puede enviar correos a la lista) o restringido a los miembros de la lista. 

Para mandar los correos, el sistema debe interactuar con otro sistema que tiene la capacidad de mandar un mail a una dirección específica. También debemos definir la interfaz con la que nos vamos a comunicar con ese otro sistema. 
Contemplar la posibilidad de que el sistema de envío de mails no pueda enviar un correo determinado. Como primera medida vamos a ignorar los mails que no se pudieron enviar. 

Cada usuario puede tener definida más de una dirección de e-mail, desde las que puede enviar mensajes a la(s) lista(s). De todas las direcciones de e-mail que tenga, una es a la que se le envían los mails. 

### Suscripción de un miembro

La suscripción también puede ser definida como abierta (cualquiera que se suscribe es admitida) o cerrada (Sólo los administradores pueden aceptar suscripciones). 

### Pie de página para la lista

El administrador del sistema puede definir un texto que se incluya como pie de página en todos los mails de esa lista.

### Nuevas formas de suscripción

Distintas formas de suscripción para los miembros de la lista de correo: mensajes individuales / resumen diario / lo miro sólo x el HTML.

### Nuevas formas de moderación

Agregamos más posibilidades de moderación: 

- Abierto
- Sólo miembros
- Los mensajes de no-miembros son moderados
- Los miembros nuevos son moderados
- Moderación de usuarios específicos: al recibir un mensaje de una dirección moderada el sistema manda el mail primero a los moderadores, con un encabezado especial. El mensaje queda en espera hasta que un moderador aprueba y entonces este mensaje se envía. Si en 5 días nadie aprueba el mensaje, este debe ser eliminado.

### Notificaciones para los moderadores

Agregar la posibilidad de que cada moderador elija si quiere recibir avisos cuando haya un nuevo mensaje para moderar. 

### Notificaciones por suscripciones nuevas

Los administradores de la lista pueden recibir mails cuando alguien requiere suscribirse a la lista (para las listas de suscripción cerrada). 

### Mejorar el manejo de envíos fallidos

- Tomar todos los mensajes fallidos y reintentarlo media hora más tarde. 
- Si falla una vez más inhabilitar la dirección de mail y no volver a intentarlo. 
- Las direcciones se pueden rehabilitar manualmente o en cualquier momento que se reciba cualquier tipo de mensaje desde esa dirección de mail.

### Recepción de mails de un usuario

Para cada lista a la que pertenezca el usuario debe tener seleccionada una casilla de e-mail de recepción distinta.

### Para analizar

- Búsqueda de mensajes enviados a la lista. 
  - Búsqueda simple: Se busca un texto determinado en el asunto del mensaje y en el cuerpo. 
  - La búsqueda avanzada permite además buscar mails: a) En los que una dirección determinada aparece como destinatario y/o como emisor del mensaje. b) Por fecha de envío. 
- Visualización de los mails por “thread”, es decir, agrupar los mails con el mismo asunto (o respuesta del asunto). 
- Posibilidad de filtrar correo de gente no autorizada. Detección de spam (para las listas abiertas). 

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Estanciero Parte 1](estanciero1.md) y [Parte 2](estanciero2.md)
