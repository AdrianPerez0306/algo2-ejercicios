
![estanciero](/images/estanciero2.png)

## Estanciero Parte 2 - Extensiones

Partiendo del [enunciado original](estanciero1.md), nos piden los siguientes requerimientos adicionales.

### Doble Turno

Cuando un jugador tira los dados y saca doble (o sea, saca el mismo número en ambos dados) al terminar el turno vuelve a tirar y moverse. 

### Jugadores

Ahora se quiere modelar a jugadores con distintas formas de compra de propiedades:

1. Hay jugadores que mientras tengan dinero para pagarlo compran lo que venga 
2. Otros sólo compran campos en provincias que ya tienen campos de otro jugador, ferrocarriles si alguien más ya compro ferrocarriles y empresas si alguien más ya compro empresas
3. Y otros jugadores sólo compran campos en la provincia de Buenos Aires y siempre que pueden compran ferrocarriles y empresas.

### Casilleros

Además, los casilleros en su mayoría son propiedades pero se decide agregar 3 nuevos casilleros: 

#### Prisión

- Cuando un jugador cae en este casillero no sucede nada. 
- Si un jugador saca más de 2 veces seguidas doble pasa a estar preso. Se debe poner al jugador en la Prisión y pierde una cantidad determinada de turnos (p.ej. estar preso 3 turnos significa que durante 3 turnos no hace nada; recién en el 4to turno desde que quedó preso puede tirar y moverse) 
- Si un jugador pasa por este casillero no sucede nada. 
Salida 
- Cuando un jugador cae en este casillero no sucede nada. 
- Si un jugador pasa por este casillero cobra $5000 del banco. 

#### Premio Ganadero

- Cuando un jugador cae en este casillero cobra $2500 del banco. 
- Si un jugador pasa por este casillero no sucede nada. 

#### Construcciones 

Se amplia el universo de construcciones que se pueden agregar a un campo. Se sigue manteniendo la regla de que para construir cualquier tipo de construcción en un campo primero se debe poseer toda la provincia. 

- **Chacras:** el precio de una chacra está especificado en el campo y varia de campo en campo 
- **Estancias:** para poder agregar una estancia en un campo primero debe haber 4 chacras en el campo y se debe pagar la suma indicada en el campo para agregar una estancia. Luego de realizada la adquisición en vez de las 4 chacras (que llamaremos chacras previas) se agrega dicha estancia. 
- **Estancias de Oro:** para poder agregar una estancia de oro en un campo previamente debe haber 3 estancias (de las anteriores) y se debe pagar una suma de $5000000. Se reemplazan las 3 estancias (que las llamaremos estancias previas) por la estancia de oro. 

Cuando un jugador cae en un campo cuyo dueño es un jugador rival (que no es un jugador con inteligencia artificial - ver más abajo) puede suceder que 

- No tenga construcciones en el campo por lo que el valor de la renta es solo el alquiler del campo 
- Si tiene construcciones el jugador debe pagar
  - Por cada chacra lo que indica el campo como alquiler por una chacra
  - Por cada estancia lo que indica el campo como alquiler por cada estancia + el alquiler que tendría cada chacra previa utilizada para construir esta estancia
  - Por cada estancia de oro se pagará el alquiler que tendrían las estancias previas + $100.000 multiplicados por la mayor cantidad de turnos de antigüedad entre todas las construcciones previas (o sea, las estancias previas y las construcciones previas de esas estancias, i.e. las chacras previas) 

#### Jugador con Inteligencia Artificial 

Como es muy complicado hacer la implementación de estos objetos se decide solo definir la interfaz que poseerán para que el día de mañana otra persona se encargue de codificarlo. Estos jugadores tienen reglas distintas que los jugadores anteriores. Si un jugador rival cae en una propiedad cuyo dueño es un jugador con inteligencia artificial (a.k.a. JugadorIA) no necesariamente este jugador le cobrará la renta sino que puede llegar a realizar cualquier otro comportamiento. Dicho comportamiento es desconocido pero debemos dejar abierta la posibilidad para que el pobre programador de un JugadorIA pueda ser parte de nuestro sistema fácilmente.

### Requerimientos

Indique las modificaciones que debería hacer al modelo del TP anterior. Se pide que su solución: 

1. Provea una forma de instanciar un tablero "bien construido"
2. Comunique claramente cómo se resuelve el comienzo del juego y el manejo de turnos
3. Siga cumpliendo con los requerimientos del TP anterior (los que no han sido modificados) + las modificaciones anteriormente descriptas 

- el nuevo manejo de turnos (cómo comienza el turno de un jugador y se pasa al turno siguiente) 
- los nuevos casilleros 
- las nuevas construcciones 
- la interfaz JugadorIA y su integración con el resto de la solución 

Puede usar: 
- Nuevos diagramas de secuencia 
- Nuevo diagrama de clases 
- Copiar diagramas anteriores agregando aclaraciones (marcando que son aclaraciones de la parte 2) 
- Codificación de los métodos solicitados y los que crea conveniente comunicar 

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Plantas vs. Zombies](plantasVsZombies.md)
