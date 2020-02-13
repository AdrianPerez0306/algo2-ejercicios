## Civilization

Una empresa desea modelar un juego al estilo Civilization. La idea es crear un modelo genérico para después sacar a la venta varias versiones del mismo como ser una épica y una futurista (al que llamarían “Capitán del Espacio”). 

El juego consiste en que un jugador controla un imperio/facción/nación/grupo-de-gente-loca, que evoluciona a lo largo del tiempo; el jugador debe dirigir la evolución del mismo mediante la administración de una serie de características. 

### Dinámica

La dinámica está dada por turnos. Cada jugador toma decisiones en su turno, y al finalizar la ronda se actualiza el estado del juego: se recauda impuestos, aumenta la población, se comprueba la felicidad de las ciudades, y otras cosas que están descriptas en el enunciado. No se pide el modelado de la dinámica, pero es fundamental conocerla para poder entender y resolver los requerimientos que se piden al final. 

### Ciudades

Cada imperio posee ciudades donde viven sus habitantes. Los imperios obtienen capacidades mediante los edificios construidos en sus ciudades. Los edificios pueden ser:

- Económicos: suman 3 puntos a la tranquilidad de los habitantes, pero no irradian cultura. Generan una cantidad determinada de dinero, que se indica para cada edificio. 
- Culturales: irradian cada uno una cantidad de cultura distinta, y otorgan a los habitantes de la ciudad una tranquilidad igual a la cultura que irradia multiplicado por un coeficiente de tranquilidad, que es el mismo para todos los edificios culturales (claro, para poder cambiarlo en cada dificultad de juego, que es menor cuanto más difícil). 
- Militares: no otorgan tranquilidad ni irradian cultura alguna, pero permiten construir unidades militares. Cada edificio militar permite construir al menos un tipo de unidad militar. Ejemplo de edificio militar: Barraca: la misma permite construir milicias. Para construir una barraca no hay ningún requisito de tecnología previo. A partir de que el imperio descubre la tecnología del Bronce, se puede construir legiones y milicias 

Cada edificio tiene un costo de construcción y un costo de mantenimiento indicados para cada uno. 

Además el juego debe poseer la posibilidad de crear Maravillas del Mundo, que son edificios especiales que irradian mucha cultura, tranquilidad y/o economía, definidas para cada Maravilla. Sólo puede existir un ejemplar para cada Maravilla del Mundo al mismo tiempo (ej.: sólo puede haber una Estatua de la Libertad en el mundo, en un momento determinado del juego). 
 
### Tecnologías

Un imperio investiga diversas tecnologías que le permiten desarrollar nuevas unidades, y edificios. Las tecnologías pueden tener como requisito la investigación previa de otras tecnologías. P. e. Para investigar Ingeniería deben desarrollarse previamente la Construcción y la Matemática.

### Unidades militares

Cuando un imperio quiere atacar a sus enemigos lo hace mediante sus unidades militares. También sirven para proteger a sus ciudades y sus habitantes. Hay distintos tipos de unidades militares, la diferencia entre ellas es el poder de ataque, el poder de defensa, y el alcance de movimiento. 

## Requerimientos

Se desea desarrollar un modelo de objetos que cumpla con las siguientes funcionalidades: 

1. Construir una unidad militar en una ciudad. Para lo cual la ciudad tiene que tener un edificio militar capaz de construir esa unidad, y la tecnología que lo permita. El Imperio tiene que tener el dinero necesario. (Tenga en cuenta que las distintas versiones del juego tendrán unidades distintas)

2. Tecnologías 
   - Mostrar las tecnologías que dispone un Imperio 
   - Cuales son las tecnologías que se está en condiciones de estudiar. 
   - Desarrollar el caso de uso de descubrir una nueva tecnología d. Determinar la velocidad de desarrollo. La cual se calcula como la suma de la velocidad de desarrollo de las ciudades, determinada por la multiplicación de los puntos de cultura y la población 

3. Construir un edificio en una ciudad, para lo cual no tiene que existir un edificio similar en la misma. Si es una maravilla entonces no tuvo que haber sido construida antes. Y el imperio tiene que tener el dinero necesario. (Tenga en cuenta que las distintas versiones del juego tendrán edificios y maravillas distintas) 

4. Recaudar impuestos. Se calcula sumando el dinero de los edificios económicos de las ciudades + un coeficiente que multiplica a la población. 

5. Felicidad 
   - Calcular la felicidad de una ciudad. Cada ciudad tiene la capacidad de tranquilizadora dada por los puntos de tranquilidad más la cantidad de unidades militares (si tiene más de 3 unidades, sólo se cuenta 3). Una ciudad es feliz si la capacidad tranquilizadora * 10000 > población. 
   - Las ciudades infelices no aportan cultura, el impuesto recaudado es de un 50%, y no producen unidades militares de ningún tipo 

## Objetivos

Se pide 

- Diagramas de clases.
- Un diagrama de objetos que muestre un imperio llamado “PDeP”, la cual tiene 3 tecnologías (Matemática, Escritura y Bronce) que permite desarrollar unidades militares milicias y legiones. La escritura permite el desarrollo de la matemática. La ciudad tiene 2 milicias, una maravilla (El coloso de Rodas que irradia 1 punto de tranquilidad), un templo (edificio cultural que irradia 1 de tranquilidad) y una barraca que permite la construcción de ambas unidades militares. Su población es de 100.000 habitantes por lo tanto la única ciudad de ese paupérrimo imperio es infeliz.
- La implementación del código que respalde el diseño

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
