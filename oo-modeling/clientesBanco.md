![banco](/images/bank.jpg)

## Clientes de un banco

### Contexto

Manejar los clientes de un banco. En particular, calcular los límites de crédito, de compra con tarjeta y de descubierto en cuenta que se pueden otorgar al cliente. También se define un riesgo total, que es la suma de estos tres límites.

Ya existe una clase Cliente que sabe devolver la info a partir de la cual se calculan estos límites, p.ej. los ingresos mensuales, el saldo total de las cuentas del cliente, y el valor de los bienes declarados por el cliente al banco. Hablando en código, la clase Cliente incluye estos métodos

```java
public double getIngresosMensuales()
public double getSaldoTotalCuentas()
public double getValorBienesDeclarados()
```

Para que sea accesible al resto de la aplicación, agregaremos en Cliente los métodos que devuelven los límites. Esto es, agregamos a Cliente los métodos

```java
public double getLimiteDeCredito()
public double getLimiteDeCompraConTarjeta()
public double getLimiteDeDescubierto()
public double getRiesgoTotal()
```

Hay distintos criterios para calcular límites, pueden diferir en ser más conservadores o más arriesgados, o en qué importancia relativa le dan a distintos factores.

En principio definamos dos criterios. Uno conservador podría ser

```
límite de crédito = ingresos mensuales x 3 + valor bienes declarados / 50    
límite de compra con tarjeta = ingresos mensuales / 2 + saldo total cuentas / 4      
límite de descubierto = valor bienes / 40
```

y otro, más arriesgado, podría ser

```
límite de crédito = ingresos mensuales x 5 + valor bienes declarados / 30 + saldo total cuentas * 2  
límite de compra con tarjeta = ingresos mensuales + saldo total cuentas / 5    
límite de descubierto = valor bienes / 30 + ingresos mensuales / 2
```

Supongamos que el oficial de cuenta asignado a cada cliente es el encargado de indicar según qué criterio calcular los límites de cada cliente; puede asignar uno al abrir la cuenta y después ir cambiándolo según cómo evoluciona el cliente.

### Agregado

Incluya un tercer criterio que sea mixto, en los cuales:


```
límite de crédito = según definido por el criterio conservador
límite de compra con tarjeta = según definido por el criterio arriesgado
límite de descubierto = según definido por el criterio conservador
```

Debe evitar que la lógica quede repetida.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Mozo la cuenta](mozo.md)
