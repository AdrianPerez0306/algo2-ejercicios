
## Sumando

### Contexto

Tenemos la siguiente clase Point2D que representa un punto en un eje cartesiano:

```xtend
import java.math.*

@Data
class Point2D implements ArithmeticValue { 
    BigDecimal x
    BigDecimal y
}
```

Es decir que tendremos:

- un constructor que espera el valor para x y para y
- no tendremos setters
- sí getters que publican las referencias x e y

### Objetivo

Poder sumar:

- un punto y un número
- un punto y otro punto

### Ayuda

- representar al número con una clase NewBigDecimal propia, que implemente una interfaz común con el `Point2D`
- implementar una solución con double dispatch o multimétodos, pensando en diferenciar la suma de puntos y la suma de números

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Animales marinos](animalesMarinos.md)
