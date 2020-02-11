
## Crear ecuaciones

### Contexto

Se toma como enunciado base [el ejercicio de ecuaciones](ecuaciones.md).

### Objetivo

Desarrollar objetos que faciliten la construcción de ecuaciones. En el ejemplo

![ecuaciones](/images/equations.png)

la forma tradicional de construir esta ecuación es:

```xtend
val dos = new Operando() => [
  value = 2.0
]
val cinco = new Operando() => [
  value = 5.0
]
val ecuacionPor = new Multiplicacion(dos, cinco)
val diez = new Operando() => [
  value = 10.0
]
val Ecuacion ecuacionMas = new Suma(ecuacionPor, diez)
```

o similar, dependiendo de los nombres elegidos para la solución y las relaciones establecidas entre operando y operador.

Considérese esta otra opción:

```java
new EcuacionBuilder(2).por(5).mas(10).build()
```

- el constructor de EcuacionBuilder admite tanto `ints` como `doubles/floats`
- también existen dos métodos interesantes: por y más. ¿Cómo trabajan?
- Por y más deberían aceptar operandos u operadores
- ¿qué devuelve el método build()?

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Crear Tablero Juego de la Vida](crearTableroJuegoVida.md)
