## Iteradores básicos

Se pide implementar los siguientes iterators. Los mismos deben respetar la interfaz `Iterator<T>` propia de Java. Esto significa que los iterators creados deben poder utilizarse de la misma manera que los ya existentes, y su comportamiento debe ser el mismo en cuanto a manejo de errores.

Los iterators pedidos son: 

### TreeNodeUpIterator

Dado un árbol de nodos, debe iterar los elementos desde un nodo x hasta el nivel más alto de la jerarquía:

![treeNodeUpIterator](/images/treeNodeUpIterator.png)

### RangoIterator

Debe iterar sobre un rango de números enteros.
¿Qué información necesita el constructor entonces? 

### LargeNumberIterator

Debe iterar sobre una lista potencialmente infinita de números, asumiendo que en el constructor le decimos:

- el valor inicial de la serie
- opcionalmente, un delta para pasar del número actual al siguiente

Ejemplos de cómo debería usarse:

```java
Iterator it = new LargeNumberIterator(1, 3);
it.hasNext()                    // esto debería dar true
it.next()                       // devuelve 1 (como objeto Long, o Integer, o BigDecimal, no nos importa tanto esto)
it.next()                       // devuelve 4 
it.next().next().next()         // devuelve 13 
it.hasNext()                    // esto debería dar true, en fin... ¿cuándo no?
```

### RandomNumberIterator

Utilizar un iterator para generar números al azar con cada llamada a `next()`. ¿Cómo implementa el método hasNext()?

### FilteredIterators

Debe iterar sobre la colección, devolviendo los elementos que correspondan a un determinado filtro. Se piden los siguientes iterators:

- elementos alternados. Ejemplo: dada la collection `[Obj1,Obj2,Obj3,Obj4]`, debe devolver solo los elementos Obj1 y Obj3 con sucesivas llamadas a next().
- elementos alternados 2: que devuelva los elementos en las posiciones múltiplo de 4.
- Strings filtrados. Iterando sobre una collection de Strings, debe devolver solo los que comiencen con "b".
- Strings filtrados 2. Idem anterior, pero debe devolver los que tengan 5 letras.

En general: para filtrar strings que cumplan una condición x, ¿cómo modelaría el criterio x de manera de poder pasar diferentes criterios en cada momento?

### IteratorOverCollectionOfCollections

Dada la Collection C cuyos elementos son a su vez Collections, este iterator permite iterar sobre todo el conjunto, tratándolo como una única Collection.

Ejemplo: dada `C = [[A1,A2,A3],[B1,B2],[C1,C2,C3,C4]]`

las sucesivas llamas a `next()` deben retornar `A1,A2,A3,B1,B2,C1,C2...`

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Manejo de turnos en juegos](manejoTurnos.md)
