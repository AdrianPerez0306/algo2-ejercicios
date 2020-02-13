![mensajería instantánea](/images/mensajeriaInstantanea.jpg)

## Mensajería instantánea

### Contexto

Se pide modelar un sistema de mensajería instantáneo con las siguientes características:

- Un usuario puede conectarse y desconectarse. Queda fuera del alcance la validación de contraseñas. 
- Un usuario tiene una lista de contactos (otros usuarios) habilitados para hablar con él. Queda fuera del alcance modelar el agregar/eliminar contactos. 
- Un usuario, si está conectado, puede enviar un mensaje a otro usuario conectado. Al hacer esto se establece una conversación entre ambos y los mensajes posteriores entre ambos usuarios deben anexarse a la misma conversación. 
- Conferencias: una vez establecida una conversación entre dos usuarios es posible agregar a un tercero (y cuarto, y quinto, etc). 
- Los usuarios en una conversación pueden decidir retirarse. 
- Al cerrar una conversación, esta puede guardarse o no, dependiendo de la configuración del usuario. Los usuarios pueden decidir: 
  - Guardar todas sus conversaciones. 
  - Guardar las conversaciones que incluyen a un usuario determinado. (Pueden elegir un conjunto de usuarios entre sus contactos.) 
  - Guardar sólo las conferencias. 
  - No guardar ninguna conversación. 

> No se pide modelar la forma en que el sistema se configura, sólo el comportamiento (guardar o no guardar la conversación) en el momento en el que un usuario abandona la conversación.

También un usuario puede enviar mensajes a un usuario desconectado, y a éste le llegarán cuando se conecte la próxima vez. 

No se pide modelar la interfaz de usuario ni la comunicación con los clientes, sólo las interfaces con esos componentes, es decir:

- Para cada evento que puede recibir el sistema indicar la forma en que el sistema recibe ese evento (objeto, mensaje, parámetros). 
- Cómo el sistema notifica a la interfaz de usuario. Para ello se pide que usen un Observer. Lo que deben determinar es: 
  - Cuál o cuáles son los objetos del dominio que deben ser observados. 
  - Cuál es la interfaz que deben implementar el o los observers. 

### BONUS

Es deseable que incluya además las siguientes características:

- Cuando un usuario se conecta, a todos aquellos que lo tengan en su lista de contactos, se les informará del hecho. En forma idéntica para cuando se desconecte.

### Solución

Hay muchas formas de resolverlo, aquí te ofrecemos [una solución posible](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnx1dG5kZXNpZ258Z3g6NjVlMmYwZjY1YzY4NDU0Mw).

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Web Server](webServer.md)
