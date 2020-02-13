![web server](/images/webServer.png)

## Web Server

Modelar un web server que resuelva los siguientes requerimientos.

### 1) Funcionalidad básica

Encontrar un archivo en su file system y enviar su contenido como respuesta a un cliente. No se pide que use sockets simplemente se debe devolver el contenido del archivo como un String. Tampoco se pide que se especifique los detalles técnicos de cómo se lee un archivo (suponga que 

```java
new File("nombre archivo").read() 
```

devuelve el contenido del archivo y tira FileNotFoundException si no existe el mismo). Si el archivo no se encuentra se debe enviar una página que incluya el texto "Error 404".

Usted debe especificar cuál es el objeto y mensaje (que incluye los parámetros) para solicitar un archivo. Asuma que hay un componente que se encarga de interpretar el pedido que llega por un socket y envía el mensaje con los parámetros correspondientes al objeto mencionado anteriormente.

El archivo puede ser pedido por HTTP o por HTTPS:

- HTTP agrega un encabezado, por lo tanto la respuesta que se debe dar al cliente es el String que se forma concatenando el encabezado http y el contenido del archivo. No se debe entrar en detalle sobre los encabezados que se agregan, basta con identificar cuál es el objeto que tiene la responsabilidad de agregar esos encabezados.
- HTTPS funciona como HTTP con la diferencia de que el contenido del archivo es encriptado. No se pide implementar el algoritmo de encriptación. Asuma que exista una clase o singleton que puede encriptar el contenido: 

```java
Cipher.encriptar(String)
```

Pasamos en limpio la secuencia:

- El usuario escribe en un browser una URL a nuestro servidor. Ejemplo: http://miWebServer.com/material/examenes/ultimoExamen.pdf
- Esto es interpretado por un componente que está escuchando el socket y recibe ese pedido. 
- El componente del punto 2 arma un pedido (http en este caso, podría ser https) para traer el archivo desde un `<directorio raíz definido para el web server que estamos construyendo>/material/examenes/ultimoExamen.pdf`. Podría ser una página html, un doc, o cualquier formato que el browser pueda entender.
- Si el archivo existe, tomamos ese contenido. Si no existe, hay que escribir un error 404 según está especificado más arriba.
- A ese contenido se le agrega el encabezado que puede ser http / https. Un objeto debe ser responsable de esto, no importa cómo se implementa.
- Se debe enviar el mensaje de respuesta a un componente para que llegue serializado vía socket a la IP que hizo el pedido. De esta parte no interesan los detalles técnicos, pero sí debe quedar clara la interfaz: qué objeto es el encargado de este punto, qué mensaje recibe y con qué parámetros.

### 2) Redirección

Se puede configurar el reenvío a otro servidor web

- **ejemplo 1**: los pedidos a `/miaplicacion/` se reenvían a `http://www.otrositio.com/otraaplicacion`
- **ejemplo 2**: los pedidos a `/otracosa/` se reenvían a `http://www.blah.com/`

En ese caso un pedido a `http://www.misitio.com/miaplicacion/index.html` se reenviará a `http://www.otrositio.com/otraaplicacion/index.html`

Indique quien tiene la responsabilidad de decidir si un pedido debe ser redirigido a otro web server

### 3) Módulos

En base al pedido se puede delegar en algún módulo anexado al web browser. Por ejemplo, las url que terminan en jsp van al módulo de java y las que terminan en php van al módulo de php. Si algunos de estos módulos no puede cumplir con el pedido, debe enviarse una página que incluya el texto "Error 500". 

No se pide que desarrollen estos módulos, pero sí que se especifique el contrato que deben cumplir y en que objeto se debe registrar (quién tiene el `addModulo()` o similar).

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Lista de Correo (versión corta)](listaCorreo.md)
