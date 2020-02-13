![lista de correo](/images/listaCorreo.gif)

## Lista de Correo (versión corta)

### Contexto

Se requiere un software que maneje listas de correo. Para entender mejor el dominio te recomendamos estos artículos:

- [Listas de correo (Capítulo de Valzacchi)](http://www.educoas.org/portal/bdigital/contenido/valzacchi/ValzacchiCapitulo-5New.pdf)
- [wikipedia](http://es.wikipedia.org/wiki/Lista_de_correo_electr%C3%B3nico)

El sistema debe contemplar: 

### Post

Enviar un correo, recibiendo la dirección de e-mail origen del correo, título y texto. El envío de correos a la lista puede definirse como

- abierto (cualquiera puede enviar correos a la lista) 
- o restringido a los miembros de la lista.

Para mandar los correos, el sistema debe interactuar con otro sistema que tiene la capacidad de mandar un mail a una dirección específica. También debemos definir la interfaz con la que nos vamos a comunicar con ese otro sistema.
Contemplar la posibilidad de que el sistema de envío de mails no pueda enviar un correo determinado. Como primera medida vamos a ignorar los mails que no se pudieron enviar.
Cada usuario puede tener definida más de una dirección de e-mail, desde las que puede enviar mensajes a la(s) lista(s). De todas las direcciones de e-mail que tenga, una es a la que se le envían los mails.

### Suscripción a la lista

Suscribir un nuevo miembro a una lista de correo. La suscripción también puede ser definida como

- abierta (cualquiera que se suscribe es admitido) 
- o cerrada (sólo los administradores pueden aceptar suscripciones).

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
