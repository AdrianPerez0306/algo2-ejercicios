
## Animales marinos

### Contexto

Definimos la siguiente interfaz para los animales marinos:

- `escaparse()`: su implementación no nos interesa en particular
- `esSaludable()`: indica si el animal es saludable
- `pelear()`: por default el animal deja de estar saludable
- `cruzarseCon(Animal otroAnimal)`: lo implementa cada animal marino concreto

Tenemos los siguientes casos que queremos modelar:

- **peces:** evitan cruzarse con los tiburones, en ese caso tratan de escaparse. Si se cruzan con otros animales, los ignoran (no hacen nada).
- **tiburones:** si los tiburones no están saludables, se escapan; si están saludables, al cruzarse con un pez lo devoran (hay un método privado devorar(Animal) que no hace falta implementar). Si se cruzan con otro tiburón se pelean.

Resuelva este requerimiento 

- sin aplicar double dispatch
- aplicando double dispatch. 

### Ayudas

- Si tu lenguaje no tiene multimétodos puede servir definir dos métodos `cruzarseConTiburon()` y `cruzarseConPez()`.
- En Xtend podés trabajar con multimétodos mediante el uso de `dispatch` methods

### Solución

Presentamos [una solución alternativa](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnx1dG5kZXNpZ258Z3g6NmViYWEyNDFmNGY1YjE5ZQ) a las dos que se piden, en el lenguaje [Cecil](http://www.cs.washington.edu/research/projects/cecil/www/cecil.html) que es prototipado (no tiene clases) y acepta multimétodos.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Regalos de cumpleaños (versión heavy)](regalosCumple2.md)
