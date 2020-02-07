![prode](/images/prode.jpg)

## PRODE

### Primera Parte

Modelar una boleta combinada de Prode (puede tener una cantidad arbitraria de dobles y triples). A una boleta se le tiene que poder pedir el precio. El precio de una boleta se calcula así:

> precio base * (2 ^ (cantidad de dobles)) * (3 ^ (cantidad de triples))

El precio base es de $5.

![boleta_prode](/images/prode_boleta.jpg)

También debe saber responder qué puso el jugador en el n-ésimo partido (algunas respuestas posibles: en el segundo partido puso Local -simple-, en el primer partido puso Local y Empate - doble-, en el tercer partido puso Local, Empate y Visitante -triple-).

## Segunda Parte

Modelar un controlador de una jugada de Prode para ser usado por Lotería Nacional.

Tiene que poder recibir una boleta, cuya info incluye DNI del jugador, la agencia donde se jugó y el monto ingresado por la agencia para la jugada. Al recibir la jugada, la lotería controla:

- que la jugada esté completa (que no haya ningún partido para el que no esté marcado ni Local, ni Empate ni Visitante). 
- que entre en fecha. Cada jugada tiene una fecha/hora límite para recibir apuestas.
- que el monto ingresado por la agencia sea correcto. Lotería Nacional debe recibir el importe de la boleta menos lo que se queda la agencia, que es: 
  - para agencias en Capital Federal: el 5% del importe de la boleta.
  - para agencias en el interior: el 5% del importe de la boleta + el mínimo entre $1 o el 3% del importe de la boleta (por gastos extras de gerenciamiento).

### Ejemplos

#### Ejemplo 1

para una boleta cuyo precio es $100,

- Si la agencia es de Capital Federal se queda con $5.
- Si la agencia es del Interior, se queda con $6
- ($5 = 5% del importe de la boleta + $1 que es < que 3% del importe de la boleta = $3).

#### Ejemplo 2

para una boleta cuyo precio es $10,

- Si la agencia es de Capital Federal se queda con $0.50.
- Si la agencia es del Interior, se queda con $0.80
- ($0.50 = 5% del importe de la boleta + $0.30 = 3% del importe de la boleta que es < que $1).

## Links

- [Volver a ejercicios introductorios](index.md)
- Siguiente ejercicio: [Agricultores](agricultores.md)
