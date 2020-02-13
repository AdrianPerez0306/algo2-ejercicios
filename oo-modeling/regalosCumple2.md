
## Regalos de cumpleaños (parte 2)

### Contexto

Tenemos el enunciado original del ejercicio regalos de cumpleaños. Clasificamos ahora los regalos en juguete, ropa y atención (lo que consideraríamos un regalo menor).

La interfaz definida para regalo se modifica a:

```java
double getValor()
Date getFechaDeEntrega()
boolean esImportado()
boolean esAzul()
```

Queremos saber ahora si un regalo que le entregamos cubre el mínimo que deberíamos gastar en cada amigo nuestro. Esto se modela en un método aparte,

```java
cubreMontoMinimo(Regalo regalo)
```

y se define así:

- Para la gente que prefiere ropa,
  - si el regalo es ropa cualquier precio está bien ($ 1, $ 500 o infinito)
  - si el regalo es una atención, ningún precio lo conforma
  - si es un juguete, el juguete debe ser importado
- Para la gente que sólo le gusta recibir el regalo el mismo día en que cumple años
  - si el regalo es ropa, debe ser mayor a $ 50
  - si el regalo es juguete, debe ser menor a $ 100 (son gente seria)
  - aceptan recibir atenciones de exactamente $ 25 (son gente rara también)
- hay gente que prefiere juguetes o ropa que salga más de 100$
  - está claro que el criterio para juguete y ropa es el mismo
  - en el caso de las atenciones, le gusta si la atención es comprada el día del cumpleaños mismo, no importa el monto.
- hay gente que le da lo mismo cualquier cosa (todo le gusta)
  - no obstante, en lo que es ropa quieren que sea azul (no importa el monto)
  - si es juguete, no debe ser azul (no importa el monto)
  - si son atenciones, el monto debe estar comprendido entre los 15 y los 25 pesos

Generar dos soluciones 

- sin aplicar double dispatch
- aplicando double dispatch

Realice un análisis comparativo entre ambas opciones, justificando ventajas y desventajas de cada una.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Seguros](seguros.md)
