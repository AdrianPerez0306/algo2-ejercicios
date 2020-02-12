
## Subastas On Line

### Contexto

Se pide modelar el dominio para un sitio de subastas online (estilo ebay, mercado libre, de remate). En dicho sistema los usuarios poseen una cuenta corriente que representa la deuda que el usuario mantiene con Subastas On Line.

Los usuarios pueden ofrecer a la venta cualquier producto, indicando el precio base y la fecha de finalización. A partir de ese momento, cualquier otro usuario puede realizar una oferta para adquirir el producto. El usuario que hace la oferta más alta al llegar al momento de finalización es quien compra el producto.

Existe un proceso que corre cada “n” tiempo, encargado de cerrar las compras finalizadas. No es necesario escribir el `main()` de dicho proceso, sí hay que codificar el método que se ejecuta periódicamente. Al cerrar una subasta, si el producto fue comprado, se debe actualizar la cuenta corriente del usuario vendedor (esto es: aumentar la deuda que el vendedor tiene con Subastas On Line). El valor a incrementar depende del producto vendido, para los inmuebles se cobra un precio fijo de $1.000, para los autos es un costo fijo de $500, para los artículos de computación es un 10% del valor total, y para el resto de los artículos, el mayor entre el 5% y $10. La cuenta corriente del comprador no sufre modificaciones por comprar u ofertar un producto.

Ej: el usuario Enzo Trossero vende un reloj con precio base de $ 20.

- El usuario Mario Goyén oferta $ 25,
- luego el usuario Carlos Killer oferta $ 28
- y la oferta finaliza.

La comisión que cobra Subastas On Line es de $ 10 (mayor que el 5% de $ 20 que es $ 1), si Enzo Trossero tiene $ 35 de deuda, aumenta $ 10 y ahora debe $ 45 (a Subastas On Line no le importa saber cuánta plata recibe Enzo Trossero ni cuánta paga Carlos Killer, sólo le interesa saber cuánta plata le debe a la empresa).

### Objetivos

Se pide

- diagrama de clases. 
- código de las partes relevantes. 
- identificar casos de uso indicando qué objeto con qué mensaje inicia cada uno. 
- describir las principales decisiones de diseño. 
- documentación adicional, sólo si el alumno considera que es necesaria para expresar su idea.

### Punto 2) Agregados

A partir del modelo realizado en el punto anterior, haga las adaptaciones necesarias para contemplar los siguientes casos (tanto en el diagrama de clases como en el código): 
Evitar que se pueda realizar una oferta entre el momento de finalización y la corrida del proceso. 
Que al finalizar una venta se pueda enviar un mail al vendedor indicando su resultado, un mail al comprador si existiese, y actualizar las estadísticas sobre la cantidad de ventas realizadas y los valores manejados por cada forma de calcular la comisión. 
Que el usuario pueda programar un valor máximo para una oferta, un valor base y un incremento, de modo tal que se oferte automáticamente el precio actual más el incremento cada vez que otro usuario supera su oferta (siempre y cuando precio actual + incremento no supere el valor máximo programado).

Ejemplo: el cliente José Percudani vende una playstation I, con precio base $ 200.

- El usuario Jorge Olguín ofrece $ 270 (oferta normal)
- El usuario Hugo Villaverde genera una oferta automática con un precio base de $ 280 (nueva oferta ganadora) incremento de $ 70 y valor máximo de $ 450. 
- El usuario Ricardo Pavoni genera una oferta automática con un precio base de $ 290 (nueva oferta ganadora) incremento de $ 50 y valor máximo de $ 550. 
- Se genera la oferta automática de Hugo Villaverde por $ 290 + $ 70 = $ 360. 
- Se genera la oferta automática de Ricardo Pavoni por $ 360 + $ 50 = $ 410. 
- No debe activarse la oferta automática de Hugo Villaverde porque $ 410 + $ 70 excede $ 450 que es el valor máximo - que quiere ofertar. 
- El cliente Claudio Marangoni ofrece $ 480 (oferta normal) 
- Se genera la oferta automática de Ricardo Pavoni por $ 480 + $ 50 = $ 530. 

**Aclaración:** siempre que haya dos ofertas automáticas, lo que sucede es que una termina venciendo (dependiendo del incremento y del valor máximo programado).

### Contexto

- La utilización del State Pattern en el punto 2.1, ¿garantiza el éxito de la solución? Justifique.
- El punto 2.2 admite resolverlo mediante un Command Pattern o a través de un Observer. Realice ambas implementaciones y compare ventajas y desventajas de cada solución.
- Resolver el punto 2.3 de dos maneras diferentes, explicando ventajas y desventajas.

### Solución

Te presentamos [una solución posible](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnx1dG5kZXNpZ258Z3g6YzYyODM0NmNiN2FjNjg5), explicada punto por punto.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Registro de incidentes](incidentes.md)
