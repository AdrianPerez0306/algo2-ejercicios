
## Manejo de Stock

### Contexto

Una empresa debe obtener los productos que vende. Para eso debe sacarlos del stock; y si no hay stock, mandarlos a construir. Para construir productos, debe conseguir componentes, que también se sacan del stock o se construyen (si no hay stock). A la vez esos componentes pueden estar compuestos por otros componentes, y asi sucesivamente, hasta que el último componente es considerado materia prima. La materia prima, la empresa la compra, no la construye. Se conoce de los componentes compuestos y productos finales la lista de componentes y cantidades que se requiere para su construcción.

Por ejemplo, para construir un auto, necesito:

- 1 volante 
- 1 motor 
- 4 puertas, donde cada una necesita 
- 1 vidrio  
- 1 chapa , que a su vez requiere
- 2 moldes de aluminio
- 2 moldes de zinc
- 1 molde de tungsteno
- 1 carrocería 
- 4 asientos

**Nota**: Hay un objeto fábrica que tiene que tiene que entender el mensaje 

```java
public void reservar(productoFinal)
```

### Primera parte

Debe reservar (descontar del stock) el producto final, en caso de que éste no existiese debe reservar todos los componentes que necesita, y los que no tenga, fabricarlos. Debe quedar claro qué componentes se reservaron y cuáles se fabricaron.

### Segunda parte

Si no hay stock del producto final y no hay stock de alguno de los elementos que hacen falta para su construcción, no se debe construir ni reservar nada.

### Tercera parte

Se incorporan las [notificaciones](manejoStockNotificaciones.md)

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Ecuaciones](ecuaciones.md)
