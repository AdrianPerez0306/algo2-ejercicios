
## Estacionamiento

Se tiene un estacionamiento de autos donde hay n autos guardados. Se puede:

- agregar un auto
- retirar un auto
- consultar los autos que están estacionados
- saber al final del día cuántos autos entraron y cuántos salieron

Al definir la interfaz de Estacionamiento se pensó en:

```java
void ingresar(Auto auto)
void retirar(Auto auto)
List getAutos()
```

Luego de algunos días se detectó un problema, dado que desde algunos puntos de la aplicación se envía el mensaje ingresar() -que cumple con todas las validaciones del negocio-, pero desde otros, se evitan las validaciones de esta manera:

```java
// desde alguna clase X que conoce al estacionamiento
Auto renault12 = new Auto()
estacionamiento.getAutos().add(renault12)
```

Para evitar este inconveniente, surgieron tres alternativas:

- Crear una clase ReadOnlyList que tiene internamente una lista
- ¿Crear una subclase de ArrayList?
- Decorar la clase ArrayList

Implemente para cada solución los métodos size, add y remove. Analice cada una de las alternativas, señalando fortalezas y debilidades, y justifique qué ventaja comparativa ofrece definir un Decorator.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Préstamo de libros](prestamoLibros.md)
