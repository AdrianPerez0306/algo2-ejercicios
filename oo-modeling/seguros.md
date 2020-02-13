
## Seguros

### Contexto

Una aseguradora trabaja con autos, camiones y taxis y ofrece tres tipos de seguro:

- contra terceros
- robo y hurto
- contra todo riesgo

Cada cliente puede contratar la combinatoria de seguros que desee (todos o alguno de ellos), siempre y cuando cumpla los criterios que establece la compañía. Para simplificar el modelo se asume que cada vehículo asegurado es un cliente distinto.

El costo de los seguros contra terceros se calcula:

- un 1,5% del valor del camión (o 2% si el camión tiene más de 10 años)
- un 1% del valor del auto
- 2% del valor del taxi + 10$ de recargo si el taxi tuvo infracciones de tránsito.

El costo de los seguros de robo y hurto se calcula:

- para los taxis y los camiones, es un 5% del valor del vehículo. Los camiones mayores a 10 años no se pueden asegurar contra robo. Lo mismo sucede con los taxis con más de 12 años de antigüedad.
- para los autos particulares, es un 3% siempre y cuando el auto haya sido fabricado en 1995 ó después. En caso contrario, se toma un 5% del valor del vehículo.

El costo de los seguros contra todo riesgo se calcula:

- solamente para autos particulares, como un 7% del valor del auto.
- los camiones y taxis no pueden contar con este seguro, por políticas de la compañía.

### Objetivo

Se pide que resuelva el costo del seguro de un cliente.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
