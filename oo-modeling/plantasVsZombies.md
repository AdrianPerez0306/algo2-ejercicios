
## Plantas vs. Zombies

Se requiere diseñar un juego de Plantas vs Zombies. En el jardín de una casa se plantan plantas mágicas capaces de defender a su casa de la amenaza de los zombies que se acercan desde la calle para comerse los cerebros de sus habitantes.

![plantas vs zombies](/images/plants-vs-zombies.png)

El jardín está dividido en parcelas: en cada una de ellas puede haber cero o más zombies, y una o ninguna planta. Además, cada parcela conoce cuales son sus dos parcelas contiguas:

![diagrama de clase](/images/plants-vs-zombies-class-diagram.png)

En cada ronda, zombies y plantas combaten, perdiendo puntos de vida. Los zombies avanzan primero, desde la calle hacia la casa (de derecha a izquierda), atacando a las plantas:

- Si en la parcela en donde está el zombie no hay planta, este avanza a la parcela de la izquierda.
- Si en la parcela en donde se encuentra el zombie hay una planta, la muerde. Cuando un zombie muerde a una planta, ésta pierde 1 punto de vida.

Luego, es el turno de las plantas, que se comportan de forma distinta según su tipo:

- **Lanzaguisantes:** le dispara un guisante a un zombie cualquiera que esté en su parcela, y si en su parcela no hay zombies, el guisante sigue de largo hacia la derecha hasta dar con un zombie cualquiera de otra parcela. Cuando un zombie cualquiera recibe un guisante, éste pierde 2 puntos de vida. 
- **Venenosas:** no atacan activamente, pero si un zombie las muerde, lo paralizan, quedando paralizado por 5 rondas. Cuando los zombies están paralizados, se quedan quietos en su lugar y no avanzan hacia la casa, pero pueden seguir mordiendo a la venenosa hasta que ésta muera (una consecuencia es que esta en tanto lo paralizará nuevamente).
- **Papas explosivas:** al pasar 5 rondas, hacen una explosión que afecta a todos los zombies de su parcela, y también de la parcela izquierda y derecha. Si un zombie sufre una explosión, muere.

Existen Zombies expeciales
- Los **Zombies Botánicos** son inmunes al veneno, y si una Venenosa trata de paralizarlos, la matan.
- Los **Zombies Cubileteros** tienen un balde en la cabeza que los protege, así que cuando sufren una explosión no les pasa nada, y cuando reciben un guisante pierden sólo 1 punto de vida en vez de 2.

Al final de cada ronda, se deben retirar del juego a las plantas y zombies muertos de cada parcela. En ambos casos se los considera muertos cuando tienen 0 puntos de vida.

### Objetivos

Se pide modelar todos los eventos antes descriptos que ocurren durante una ronda. Está fuera del alcance del ejercicio modelar la dinámica del juego por la que se va pasando de ronda en cada parcela, y la salida y llegada de zombies desde la calle y a la casa.

Considerar los siguientes escenarios:

1. Pasa una ronda en una parcela sin planta y un zombie normal. No olvidar considerar el caso en que el zombie esté paralizado.
2. Pasa una ronda en una parcela con un lanzaguisantes y 2 zombies normales.
3. Pasa una ronda en una parcela con un lanzaguisantes y sin zombies. En la parcela siguiente hacia la derecha tampoco hay zombies, pero en la siguiente de esa hay un zombie cubiletero.
4. Pasa una ronda en una parcela con una planta venenosa, un zombie normal y un zombie botánico.
5. Pasa una ronda en una parcela con una papa explosiva. En la parcela misma no hay zombies, en la parcela a la derecha hay un zombie normal y en la parcela izquierda hay un zombie cubiletero.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Civilization](civilization.md)
