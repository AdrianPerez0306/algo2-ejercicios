
## Préstamo de Libros

### Contexto

Una biblioteca que presta libros a sus socios. Para ello no deben tener deuda pendiente.

Tenemos las siguientes entidades:

- Socio
- Libro

La interfaz de Socio es:

```java
int antiguedadDesde(Date hoy) // antigüedad desde una fecha, medida en meses
double montoDeuda()           // deuda total en pesos
boolean esMoroso()            // indica si tiene deuda
void prestar(Libro libro)     // se permite prestar un libro si pasa las validaciones
```

La interfaz de Libro es:

```java
void validarPrestamo(Socio socio) // realiza la validación del préstamo a un socio particular
void prestarA(Socio socio)        // cambia su estado interno para reflejar que está prestado
boolean prestado()                // indica si está prestado
```

### Validaciones adicionales

Se quiere agregar los siguientes requerimientos:

- Ciertos libros se pueden prestar aunque el socio tenga deuda. El monto máximo de la deuda que puede mantener el socio depende del libro. La promoción es por tiempo limitado
- Algunos libros (de valor sentimental para la Biblioteca) sólo se pueden prestar si el socio tiene una antigüedad de 6 meses o más
- Por último, algunos libros de especial seguimiento deben auditarse, enviando un mail a un administrador con la fecha y hora, socio al que se prestó y el libro en cuestión.

Tener en cuenta que los libros pueden combinar estas características (ser sentimentales y poderse prestar aún cuando tenga deuda, ser sólo sentimentales, etc.)

Implemente la solución y los tests unitarios utilizando decoradores.

