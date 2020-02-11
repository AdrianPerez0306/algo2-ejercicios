
## Juego de la Vida

El ejercicio consiste en realizar el diseño del [juego de la vida](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), ideado por el matemático John Conway en 1970. El juego consta de un tablero con casilleros (similar al de ajedrez), cada casillero puede tener adentro un bicho o estar vacío.

![juego de la vida](/images/JuegoDeLaVida1.png)

[(link al juego on-line)](https://bitstorm.org/gameoflife/)

En amarillo se muestra un casillero con un bicho y en gris quedan los casilleros vacíos. Si dos casilleros contiguos están ocupados por un bicho se dice que esos bichos son vecinos. Ej:
 
![casillero](/images/JuegoDeLaVida2.png)

El juego comienza colocando X cantidad de bichos en cualquiera de los casilleros del tablero (X debe ser mayor a 0). Una vez que queda establecida la configuración inicial del tablero el juego comienza. Por cada generación que pasa (equivalente a un turno o una mano) en todos los casilleros vacíos que tengan dos o tres vecinos nace un bicho, mientras que para los bichos:

- Si tienen menos de dos vecinos mueren de soledad 
- Si tienen más de tres vecinos mueren por sobrepoblación (les falta comida) 
- Si tienen dos o tres vecinos alcanzan el equilibrio en su contexto y entonces sobreviven. 

Las generaciones pasan de manera sincrónica, lo que significa que primero se evalúa la configuración del tablero y luego nacen o mueren los bichos (de manera tal que no importa por que lado del tablero se comience, el resultado siempre será el mismo). El juego termina cuando el sistema se vuelve estable, o sea, cuando se repite el mismo tablero, o bien cuando no quedan más bichos.

El juego permite generar “patrones” donde se configuran los bichos de una manera y se puede llegar a una población estable al cabo de algunas generaciones. Por ejemplo, el siguiente patrón:

![patrón pobre](/images/JuegoDeLaVida3.png)

Produce que al cabo de unas generaciones toda la población de bichos se extinga:

![simulación patrón pobre](/images/JuegoDeLaVida4.png)

Por otra parte, tenemos patrones que terminan oscilando entre dos estados, como por ejemplo el “blinker” que actúa así:

![blinker](/images/JuegoDeLaVida5.png)

De la misma manera oscila esta figura, conocida como “sapo”:

![sapo](/images/JuegoDeLaVida6.png)

### Primera parte

Se pide:

- Excluir la generación del tablero, asumir que el tablero ya está construido. 
- Modelar la dinámica general del juego, esto es
  - determinar condiciones para continuar o terminar el juego
  - recorrer las celdas o casillas del tablero
- Manejar el estado de una celda o casilla
  - determinar si un bicho nace, sobrevive o se extingue para eso 
  - saber si tiene la suficiente cantidad de vecinos
- Actualizar el estado del tablero, para esto hay que considerar que primero se deben evaluar todas las casillas, entonces hay que separar
  - el momento en que determino el estado a futuro de la celda o casilla
  - el momento en que ese estado pasa de "futuro" a "actual" (un "commit")

### Agregado

_Cambiando las generaciones_: Se puede hacer que el paso de las generaciones sea asincrónico, o sea que por cada bicho que muere o nace hay que evaluar nuevamente el tablero. De esta forma cambia mucho el juego dependiendo del casillero y la dirección por la que se empiece a evaluar (para que tenga gracia debería ser random). La actualización asincrónica consiste en:

1. elegir una parcela (eligiendo criterio al azar o determinístico)
2. calcular si en esa parcela debe nacer un bicho, o si debe morir el individuo en esa parcela.
3. actualizar el estado para esa parcela, obteniendo el nuevo estado actual.

## Objetivos

Se pide:

- separar el criterio por el cual se elige una parcela de manera que sea fácil modificar la forma en que se selecciona la parcela/casilla/celda: que sea aleatoria, el primero, por fila, etc.
- hacer las modificaciones necesarias para que el juego admita dos modalidades
  - sincrónico: se evalúan todas las parcelas primero y luego se aplica el cambio (el bicho nace, sobrevive o muere)
  - asincrónico: se evalúa una parcela (por un criterio x) y se aplica inmediatamente el cambio (el bicho nace, sobrevive o muere afectando a todos sus vecinos)
- BONUS: permitir deshacer el cambio de toda una generación de bichos (sólo una generación hacia atrás).

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
