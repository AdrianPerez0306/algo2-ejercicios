
## Sistema de Gestión de Incidentes

### Parte 1

Se desea modelar un módulo de gestión de incidentes para un muy exclusivo bar, el cual será utilizado por otros sistemas. La funcionalidad principal del mismo es llevar un registro histórico de los incidentes (log), que serán ingresados en el sistema para ser consultados más tarde.

Los tipos de incidentes identificados hasta el momento son los siguientes:

- Detección de persona violenta. Se debe registrar la información de la persona.
- Principio de incendio. Se debe registrar el motivo, si se lo conoce. 

Es probable que haya que soportar algunos pocos tipos de incidentes más (2 ó 3 como mucho)

La funcionalidad de consulta de incidentes será inicialmente muy simple: permitirá listas los eventos que hayan ocurrido después de un cierto momento. 

Además, nos precisaron que el sistema tiene que integrarse con otros módulos externos al sistema, algunos de los cuales desarrollaremos, y otros que ya fueron desarrollados por otro equipo. Algunos de estos sistemas están desarrollados en otras tecnologías. 

Estas integraciones consistirán en ejecutar ciertas acciones contra estos módulos ante la ocurrencia de un incidente. Por ejemplo: 

- Detección de persona violenta:
  - Informar por biper del sistema de prevención.
  - Agregar al violento a un sistema que gestiona listas negras.
- Principio de incendio
  - Informar al sistema de prevención para que dé inicio el proceso de desalojo
  - Llamar a la línea de alerta de bomberos.

Si el sistema tiene éxito, es probable que la cantidad de integraciones con otros sistemas crezca exponencialmente. Algunas de las integraciones las construiremos nosotros, pero otras serán delegadas a otros equipos que no trabajarán en el desarrollo de este sistema de seguridad. 

Además, según ciertas configuraciones iniciales, algunas integraciones podrían agregarse o quitarse. 

Se pide proponer una solución:

- comunicando su diseño general 
- indicando sus interfaces entrantes y salientes al sistema

### Parte 2

Unos meses después….

Nos encontramos utilizando el componente desarrollado sin inconvenientes, pero surgieron algunos nuevos requerimientos a tener en cuenta:

- No deberían poder registrarse eventos en un sector que se encuentre cerrado.
- Como hemos detectado que todas las operaciones que involucran al componente son muy lentas, deseamos poder loguear cuando arranca y cuando termina cada registración.
- Si el incidente tiene un tag especificado (por configuración) deberá enviarse un mail al administrador con la información de dicho incidente.

Se pide proponer una solución para los anteriores requerimientos, teniendo en cuenta:

- Al igual que las integraciones, las acciones, deberían poder configurarse de forma simple.
- No se podrán hacer cambios en el código del componente externo, ya que:
  - Si se piden cambios hechos en el componentes si no son triviales suelen demorar.
  - Agregar el logger, solo va a ser utilizado en algunas pruebas, lo cual no justifica que se agregue al componente externo.
  - La biblioteca no tiene test para validar su funcionamiento.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
