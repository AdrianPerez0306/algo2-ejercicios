
## Estanciero Parte 1 

Se dispone de un tablero con casilleros, los casilleros en su mayoría representan propiedades donde cada propiedad tiene un nombre y un precio de compra inicial. 

Algunas propiedades son "Campos" y están agrupadas en grupos de 2 ó 3 llamados "Provincias". 

Se juega de 2 a 6 jugadores. Cada jugador mueve en su turno su ficha a través del tablero según lo que indiquen los dados (2 dados). Cada jugador arranca con un capital inicial de $1.000.000 

### Caída en una casilla 

Cuando un jugador cae en una propiedad pueden ocurrir tres cosas: 

1. Que la propiedad no pertenezca a nadie (es decir, que el dueño es el Banco): el jugador tiene la opción de comprar dicha propiedad - por ahora siempre que tiene el dinero suficiente la compra pero esto puede cambiar 
2. Que el dueño de la propiedad sea un jugador rival: el jugador debe abonarle al propietario el valor de la renta de esa propiedad. 
3. Que la propiedad sea de uno mismo: no pasa nada 

### Objetivo

El objetivo del juego es hacer que todos los rivales queden en bancarrota, es decir sin propiedades y sin dinero. 
Para lograr el objetivo los jugadores deben comprar propiedades y en lo posible formar provincias ya que estas permiten la construcción de estancias (por si alguien se pregunta, en este modelo no existen las chacras) y con esto aumentar considerablemente el valor de la renta percibida (recordar que la renta se percibe cada vez que un jugador contrario cae en una propiedad nuestra). 

### Detalles

#### Tipos de Propiedades

**Campos:** Son las propiedades que forman parte de una provincia, cada propiedad tiene un valor de renta fijo y además un valor de renta para los casos en que la propiedad tenga construida 1, 2, 3, 4 y 5 estancias. También consta el costo de construcción por cada estancia. 

Ejemplo:

| Campo | Buenos Aires Zona Norte |
| ----- | ----------------------- |
| Cantidad de Estancias | Renta |
| Sin Estancias | $ 3.000 |
| Con 1 Estancia | $ 20.000 | 
| Con 2 Estancias | $ 62.000 |
| Con 3 Estancias | $ 123.000 |
| Con 4 Estancias | $ 215.000 |
| Con 5 Estancias | $ 310.000 |
| Costo de construcción de c/estancia | $ 50.000 |

**Construcción de estancias:** Deben hacerse en forma pareja, es decir no puedo construir 3 estancias en un campo y ninguna en otro campo de la misma provincia. La máxima diferencia permitida es de 1 estancia.

**Ferrocarriles:** Son cuatro ferrocarriles en todo el tablero, los cuatros pertenecen al mismo grupo, en ellos no se pueden construir estancias, pero conviene acumularlos ya que la renta aumenta al tener mayor cantidad de los mismos. Ejemplo: Si tengo un ferrocarril me pagan $30.000 de renta, pero si tengo 2 me pagan $80.000, etc.

**Empresas de Servicios:** Son sólo dos en todo el tablero y la renta que se cobra es $20.000 * X en el caso de poseer sólo una de las dos empresas y $50.000 * X en caso de poseer las dos empresas. Tampoco se pueden construir estancias y pertenecen _a un mismo grupo_. Se deben tirar los dados cuando se cae en una empresa y X representa el valor que suman los dados.

Ya se cuenta con una clase **Tablero** a medio implementar, lo único que está completamente desarrollado es el método `casillerosDesdeHasta` que recibe un casillero y un número, devuelve una colección ordenada de casilleros donde el primer elemento es casilleroInicial, el segundo es el casillero siguiente a casilleroInicial y así, siendo el último elemento de la colección el casillero que está a unNumero de posiciones de casilleroInicial.

Usted puede agregar/modificar/quitar lo que crea necesario.

### Requerimientos 

Debe proponer una solución para los siguientes puntos: 

- **Inicialización del juego.** Establecer los jugadores, repartir plata inicial a cada uno y 
ponerlos en la casilla de salida 

- **Ejecución de un turno.** Se debe especificar detalladamente:
  - tirar los dados 
  - movimiento del jugador 
  - acciones necesarias debido al lugar donde cayó el jugador (ver Caída en una casilla) 

- **Construcción de estancias**
  - en cualquier momento un jugador puede comprar estancias en alguno de sus campos 
  - no importa cómo decide el jugador esto, solo le envía el mensaje #agregarEstancia - sin parámetros - a quien corresponda 
  - recordar que no se permite una diferencia mayor a 1 entre las estancias que tienen los campos de una provincia 
  - si no se puede realizar la construcción que se lance un error 
  - en caso de que la construcción sea posible se le debe descontar el dinero correspondiente al dueño del campo 

- **Bancarrota.** Si al momento de pagar la renta un jugador no tiene dinero ese jugador queda fuera de juego. Esto significa que el jugador debe devolver sus propiedades al banco y abandonar el juego ergo no participa en los próximos turnos. 

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Estanciero Parte 2](estanciero2.md)
