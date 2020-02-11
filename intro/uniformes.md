## Uniforme

### El problema

Pepero S.A. fabrica uniformes. A partir de modelos básicos que arma en su planta, después la lleva a varios talleres que le pueden hacer agregados y cambios. De cada prenda sabemos:

- en qué material está construido
- el color, que pueden manejar como un String, p.ej. "rojo", o como una enumeración (enum)
- la leyenda que tiene estampada, que es un String, p.ej. "Cacho SRL"
- cuántos refuerzos tiene
- cuántas costuras extra le hicieron 

El grado de resistencia de un uniforme se mide en pepines: un uniforme de 3 pepines es más resistente que uno de 2. La resistencia de un uniforme se calcula como la resistencia de su material más medio pepín por cada refuerzo que le ponen. A este subtotal se le agrega un 20% adicional por cada costura extra. P.ej. si el lino tiene 4 pepines de resistencia, un uniforme de lino con 2 refuerzos y 3 costuras extra tiene

> (4 + (0.5 * 2)) * 1.6 = 8 pepines

Existen distintos tipos de clientes: en principio, fábricas y oficinas, pero podrían agregarse más a futuro. Cada cliente exige que las prendas que se le entreguen tengan estampado el nombre de la empresa. Además:

- las fábricas necesitan uniformes cuyo grado de resistencia supere un valor que establece cada fábrica. No tienen pretensiones respecto del color.
- las oficinas necesitan uniformes que sean de un color determinado, que determina cada oficina. No tienen requerimientos sobre la resistencia.
- Cada cliente paga un valor por cada uniforme, que se pacta entre Pepero S.A. y el cliente.

## Requerimientos

1. saber el grado de resistencia de un uniforme.
2. poder saber si un cliente acepta un uniforme, esto es
  - si es del color correcto 
  - si tiene el grado de resistencia suficiente

## Pruebas

Codificar los siguientes casos de prueba.

### Fixture

- Al material lino que tiene 4 pepines de resistencia
- Al material algodón que tiene 9 pepines de resistencia
- Un uniforme (uniforme 1) de lino de color rojo con 2 refuerzos y 3 costuras extra. 
- Otro uniforme (uniforme 2) de algodón de color negro con 5 refuerzos y sin costuras extra
- La oficina manliba quiere uniformes de color rojo
- La fábrica inducol quiere trajes de al menos 9 pepines de resistencia.

### Casos

| Caso de prueba | Resultado esperado |
| ------------- |-------------|
| Medir la resistencia del uniforme 1 | **8** |
| Medir la resistencia del uniforme 2 | **11.5** (9 resistencia base del algodón + 0.5 * 5 refuerzos = 9 + 2.5) |
| Preguntar si manliba acepta el uniforme 1 | **Sí**, el uniforme 1 es rojo y manliba quiere uniformes de ese color. |
| Preguntar si manliba acepta el uniforme 2 | **No**, el uniforme 2 es negro y manliba quiere uniformes rojos. |
| Preguntar si inducol acepta el uniforme 1 | **No**, el uniforme 1 tiene una resistencia de 8 pepines < 9 |
| Preguntar si inducol acepta el uniforme 2 | **Sí**, el uniforme 1 tiene una resistencia de 11.5 pepines > 9 |

## Links

- [Volver a ejercicios introductorios](index.md)
- Siguiente ejercicio: [Uniformes - Segunda parte](uniformes2.md)
