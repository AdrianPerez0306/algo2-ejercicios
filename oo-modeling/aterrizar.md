
## Aterrizar.com

Hace algunos años, tuvimos unos clientes para los cuales desarrollamos un sistema para vender boletos de avión por Internet. En ese entonces, nos solicitaron que implementáramos la venta de asientos (que representan los pasajes o  boletos).  Ahora, estos clientes han vuelto, y nos piden soportar una nueva política de ventas.

Hasta el día de la fecha, los asientos podían estar o libres o vendidos (con un simple flag estaVendido bastaba), pero la nueva política introduce el concepto de reservas al negocio. La idea es que un usuario pueda reservar un asiento que se encuentre libre, en vez de comprarlo.

Además, se pide implementar las sobre-reservas. Un usuario sobre-reserva un asiento cuando este ya está reservado por otro. La ventaja de esto es que en caso de que se cancele o se pierda una reserva, el usuario que sobre-reservó primero tendrá prioridad para comprar el asiento (y si este no lo desea, la posibilidad será del que le sigue). La cantidad de sobre-reservas posibles sobre un asiento no está limitada.

En síntesis, las acciones a realizar con un asiento serían:

- Comprarlo
- Reservarlo
- Sobrereservarlo
- Desreservarlo

Con las siguientes consideraciones:

- Los asientos libres pueden comprarse o reservarse.
- Los asientos reservados pueden ser comprados por la primer persona que hizo la reserva, o ser sobre-reservados por otra.
- Los asientos vendidos no pueden ser ni reservados ni vendidos. Tampoco se puede cancelar la venta.
- Cuando se produce la compra, se deben realizar una serie de acciones particulares
- En todo momento nos interesa saber quiénes son los usuarios que tienen reservado o sobre-reservado al asiento.

Se pide la implementación de la venta y reserva de asientos respetando la nueva política de la empresa.

> La implementación de la caducidad de la reserva queda fuera del scope de este requerimiento.

## Consigna

- Hacer un diagrama de estados 
- Proponer una solución

## Links

- [Volver a ejercicios de modelado con objetos](index.md)

