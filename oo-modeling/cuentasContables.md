
## Cuentas contables

### Contexto

Se necesita modelar un sistema contable, que permita conocer el saldo de dos tipos de cuenta:
las que tienen asociadas cuentas hijas (son integradoras) y 
las que no (son imputables). Sólo éstas tienen movimientos que figuran en el libro Diario. 
Ejemplo:

```
1. Activo (cuenta integradora)
  1.1 Activo Corriente (cuenta integradora)
    1.1.1 Caja (cuenta imputable)
    1.1.2 Bancos (cuenta imputable)
    1.1.3 Plazos Fijos ...
  1.2 Activo No Corriente ...
```

Si tenemos

Inicio de actividades de “Negocio Tito” – 12/05/2004
Libro Diario

| Fecha | Asiento | Cuenta Debe | Cuenta Haber | Debe | Haber |
| ----- | ------- | ------      | -----        | ----: | -----: |
| 12/05/2004 | 1 | Caja | | 100 | | 
|  |  |  | a Ventas | | 100 | 
| | 2 | Compras | | 50 | | 
|  |  |  | a Caja | | 50 | 

Al pedirle el saldo a Activo nos debería devolver 50.

### Objetivos

Se pide

- Conocer el saldo actual de una cuenta
- Conocer el saldo de una cuenta a una fecha determinada
- Defina la forma de representar un asiento, sabiendo que cada asiento tiene un conjunto de cuentas que pueden formar - parte del debe o haber. Debe quedar claro para la persona que codifique la interfaz de usuario cómo distinguir las - cuentas y los importes ($$) del debe y del haber.
- Saber qué asientos hubo en una fecha determinada
- No permitir que una cuenta integradora participe de un asiento (ejemplo:  no debe poderse armar un asiento con la cuenta Activo Corriente)

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
