
## Manejo de turnos en juegos

### Ajedrez (sencillo)

Modelar un iterator que permita manejar la dinámica del juego de ajedrez, donde sabemos que:

- hay dos objetos jugador (uno representa las blancas y el otro las negras)
- hay un objeto Juego al que puedo enviarle el mensaje: boolean termino()
- en ajedrez los jugadores se van alternando las movidas sucesivamente

Preguntas: 

- ¿Qué necesita el constructor del Iterator?
- ¿Qué devuelve el método next()?
- ¿Cómo implementa el hasNext()?
- ¿Tiene sentido implementar el método remove()?

### Truco (difícil)

Modelar un Iterator que permita manejar la dinámica de un partido de truco de 6 personas. Algunas ayudas:

- Es importante conocer el orden inicial de los jugadores
- Hay que identificar cuándo se terminó la mano
- Si los jugadores juegan una carta "tapada" (dada vuelta) no impacta al diseño del iterator
- Modelar quién fue el ganador de la mano es un ejercicio interesante pero distrae el foco de atención de el presente ejercicio, sugerimos buscar un objeto que nos diga quién fue el ganador de la mano. Esto permite que nos concentremos en buscar que el método next() resuelva correctamente el jugador que arranca la segunda mano y cómo sigue la mano en general
- Lo mismo ocurre cuando un jugador canta truco y el otro jugador desiste: no nos interesa modelar esta situación
- ¿Qué cambiaría si el partido de truco es de 4 ó 2 personas?

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
