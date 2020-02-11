
## Notificaciones al manejo de stock

### Contexto

Tomando como base el ejercicio de [manejo de stock](manejoStock.md), en el cual tenemos un depósito que almacena distintos productos (simples y compuestos), nos interesa hacer los siguientes agregados:

Cada producto define 

- la cantidad mínima
- y máxima del stock a almacenar
- y cuál es el punto de pedido, que es la cantidad que va a pedir cada vez que compre.

Cuando sale del depósito un componente/materia prima

- debe generarse un pedido de compra si el producto bajó por sobre su stock mínimo. Para ello se registra el producto y la cantidad a pedir. Luego el departamento de Compras toma esta información y arma la nota de compra en base a la cotización del proveedor (lo que hace el Departamento de Compras está fuera de alcance del ejercicio)
- algunos productos al bajar el stock mínimo generan un log de auditoría con fecha, producto y el alerta de que bajó el stock mínimo (marcado como un string que contiene un mensaje representativo para el usuario). Esto varía mes a mes según la balanza comercial de nuestro país, lo que se pide es que el sistema se adapte rápidamente a este requerimiento.
- para algunos productos nos interesa enviar un mail si un determinado producto tuvo una salida de más de x unidades. No se pide implementar el envío de mail propiamente dicho sino asegurar que haya un objeto responsable de ésto y que tenga toda la información disponible.
- es posible que en un futuro se agreguen nuevos "interesados" en hacer algo cuando haya una salida de stock.

Adicionalmente, cuando ingresa mercadería:

- algunos productos registran en el log de auditoría cuando dejan de estar por debajo del stock mínimo. Ejemplo: si el stock mínimo del producto "Válvula cilíndrica de amonio" es de 10 unidades y hay actualmente 7 unidades, al ingresar 5 unidades al stock pasa a tener 12 unidades > 10, si se definió que interesa loguear este evento debe generar un registro de log de auditoría con fecha de hoy, el producto correspondiente y una descripción representativa.
- otros productos avisan cuando al ingresar mercadería exceden el stock máximo posible. Ejemplo: si el producto  "Válvula cilíndrica de amonio" tiene un stock máximo de 20 unidades, había 18 unidades e ingresan 3 piezas más, si se definió que interesa loguear este evento debe imprimir por consola el producto y el mensaje correspondiente.
- es posible que en un futuro se agreguen nuevos "interesados" en hacer algo cuando haya una entrada de stock.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Reserva de libros](reservaLibros.md)
