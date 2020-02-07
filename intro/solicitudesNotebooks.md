![notebooks](../images/notebooks.jpg)

## Solicitudes de notebooks

### Contexto

Una empresa define solicitudes para entregar notebooks a sus empleados. Para aprobar una solicitud la misma debe tener la firma del gerente inmediato y el empleado tiene que pertenecer a un sector que acepte movilidad (esto lo determina el sector).

La solución pensada por el programador fue:

```java
// Clase Solicitud 
public int procesar() {
   if (this.firmaGerente() == null) {
      return -1; // No está aprobado por el gerente
   }

   if (this.empleado.getSector().tieneMovilidad()) {
      return -2; // El empleado es fijo
   }
   ...
}
```

- Modifique el método procesar para que trabaje con excepciones chequeadas.
- Modifique el método procesar para que trabaje con excepciones no chequeadas.
- Compare ambas soluciones, buscando fortalezas y debilidades de cada una.

### Segunda parte

Hay una clase que se encarga de procesar mensualmente todas las solicitudes de notebooks, codificada de la siguiente manera: 

```java
// Clase ProcesoMensualSolicitudes
public int procesarSolicitudes(List solicitudes) {
   for (Solicitud solicitud : solicitudes) {
      int result = procesar();
      if (result == 0) {
         ...
      } else {
         this.loguearRechazo(solicitud);
         return -1;
      }
   }
}
```

Si alguna de las solicitudes falla todo el lote a procesar debe fallar.

- ¿Cómo modificaría el método para trabajar con excepciones?
- ¿Qué ventaja presupone? Justificar.

## Links

- [Volver a ejercicios introductorios](index.md)
- Siguiente ejercicio: [Pepita Testeada](pepitaTesteada.md)