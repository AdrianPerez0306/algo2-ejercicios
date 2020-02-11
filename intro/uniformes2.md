
### Uniformes Segunda parte

### El problema

Se desea realizar los siguientes cambios y agregados sobre el dominio de uniformes:

Cuando se fabrica un uniforme, ya se sabe para qué cliente es, al centro de procesamiento llega con el cliente ya asignado. Un uniforme registra ahora sus movimientos de stock desde que llega al centro de procesamiento hasta que se entrega al cliente. Cada movimiento de stock tiene una fecha y el destino (un taller o centro de procesamiento).

Para poder trabajar sobre los uniformes, hay que colaborar con varios tipos de talleres:

- **tintorerías normales**: pueden teñir uniformes de determinados materiales, y sólo a determinados colores.
- **tintorerías grosas**: pueden teñir cualquier uniforme a cualquier color. 

Los talleres llevan un registro de los uniformes que tienen trabajos pendientes.

Pepero S.A. tiene varios centros de procesamiento, a los que les van llegando los uniformes a medio hacer. Cada centro de procesamiento trabaja con un conjunto de talleres (y cada taller sabe cuál es su centro de procesamiento). La planta donde se hacen los uniformes está fuera de este modelo, cada uniforme llega de alguna forma a un centro de distribución, y el centro tiene la responsabilidad de llevarlo a los talleres que haga falta para que tenga todo lo que necesita el cliente, y después enviárselo al cliente (para lo cual tiene que registrar los uniformes que tiene pendientes de entrega).

El centro de procesamiento conoce la lista de envíos que hizo, donde un envío registra la fecha, el cliente al que está dirigido y la lista de uniformes cuyos trabajos se completaron según el requerimiento del cliente. 

## Requerimientos

A los requerimientos de la primera parte, se agrega:

1. Determinar si un uniforme está listo (cuando ya se puede entregar), esto es que está todo ok (en cuanto a color y grado de resistencia pedido por el cliente).
2. Registrar el envío de un uniforme a un taller (para el taller sería un ingreso). Debe
  - validar que tenga sentido enviar al taller (el uniforme no debe estar listo)
  - validar que el taller pueda aceptarlo, esto es
  - las tintorerías grosas aceptan cualquier uniforme
  - las tintorerías normales deben poder trabajar con el material del uniforme y con el color que quiere el cliente
  - en caso de no pasar alguna validación lanzar una excepción
  - generar un movimiento de stock para el uniforme con fecha del día y destino el taller
3. Registrar el trabajo que hacer el taller sobre un uniforme. Al finalizar el trabajo el uniforme vuelve automáticamente al centro de procesamiento. ¿Qué se hace en cada caso?
  - Las tintorerías tiñen el uniforme del color que necesita.
  - También debe generar un movimiento de stock para el uniforme con fecha del día y destino el centro de procesamiento
4. Manejar las entregas de uniformes listos a los clientes para un centro de procesamiento.
5. Se genera un objeto Envío que registra de qué cliente se trata, la fecha en que se hace el envío y
los uniformes entregados, y se asocia al centro de procesamiento.

## Casos de prueba

### Fixture o Juego de datos general

Se deben crear los siguientes objetos comunes a todos los tests:

- Material lino que tiene 4 pepines de resistencia
- Material algodón que tiene 9 pepines de resistencia
- Uniforme (uniforme 1) de lino de color rojo con 2 refuerzos y 3 costuras extra.
- Uniforme (uniforme 2) de algodón de color negro con 5 refuerzos y sin costuras extra
- Uniforme (sacoAzul) de algodón de color azul sin refuerzos y sin costuras extra.
- Uniforme (pantalonBlanco) de lino de color blanco con 1 refuerzo y sin costuras extra.
- Oficina manliba quiere uniformes de color rojo
- Fábrica inducol quiere trajes de al menos 9 pepines de resistencia.
- uniforme1 está asignado a la oficina manliba.
- uniforme2 está asignado a la fábrica inducol.
- sacoAzul está asignado a la oficina manliba.
- pantalonBlanco está asignado a la oficina manliba.
- Tintorería grosa nakasone.
- Tintorería normal higa, que trabaja con colores rojo y azul y materiales de algodón.
- Tintorería grosa nakamura.
- El centro de procesamiento liniers trabaja con las tintorerías nakasone e higa.
- El centro de procesamiento mataderos trabaja con la tintorería nakamura.
- El centro de procesamiento liniers recibió los uniformes uniforme2 (de inducol), sacoAzul y pantalonBlanco (que están asignados a manliba).
- El centro de procesamiento mataderos recibió el uniforme uniforme1 (que está asignado a manliba).

| Caso de prueba | Resultado esperado |
| ------------- |-------------|
| 1 Medir la resistencia del uniforme 1	| **8** |
| 2 Medir la resistencia del uniforme 2 | **11.5** (9 resistencia base del algodón + 0.5 * 5 refuerzos = 9 + 2.5) |
| 3 Preguntar el uniforme 1 está listo | **Sí**, el uniforme 1 es rojo y manliba (el cliente asignado) quiere uniformes de ese color. |
| 4 Preguntar si el sacoAzul está listo |	**No**, el sacoAzul es azul y manliba (el cliente asignado) quiere uniformes rojos. |
| 5 Preguntar si el uniforme 2 está listo	| **Sí**, el uniforme 1 tiene una resistencia de 11.5 pepines > 9 que es lo que pretende inducol (el cliente asignado) |
| 6 Tratar de enviar el uniforme1 del centro de procesamiento liniers a la tintorería higa. | **No debe poderse**, ya que no tiene sentido (el uniforme 1 está listo). Consejo: esto se debe hacer esperando que ingresar el uniforme1 a la tintorería higa de error, si no da error el test debe fallar. |
| 7 Tratar de enviar el pantalonBlanco del centro de procesamiento liniers a la tintorería higa. | **No debe poderse**, ya que el taller no permite al lino como material. Consejo: esto se debe hacer esperando que ingresar el uniforme1 a la tintorería higa de error, si no da error el test debe fallar. 
| 8 Tratar de enviar el sacoAzul del centro de procesamiento liniers a la tintorería higa. | **Debe poderse**, de manera que al final del test se verifique que: el sacoAzul esté dentro de los uniformes pendientes de trabajar por parte de higa, el sacoAzul tenga un nuevo movimiento de stock. |
| 9 Verificar que el test anterior no tuvo efecto colateral. | Debe verificarse que la lista de uniformes pendientes de la tintorería higa esté vacía. Entonces el envío simulado en el test anterior no trajo efecto colateral (tuvo efecto sólo dentro del test anterior) |
| 10 Registrar: el envío del sacoAzul del centro de procesamiento liniers a la tintorería higa, el trabajo de la tintorería higa sobre el uniforme1 | El sacoAzul debe ir del centro de procesamiento liniers a la tintorería higa y volver de allí a liniers nuevamente.	Debe verificarse que: el sacoAzul tenga dos movimientos de stock. Además el saco azul debe quedar listo (ok para el cliente asignado, esto quiere decir que debe quedar teñido de rojo). No hace falta chequear que el color sea rojo, basta con verificar que esté listo |
| 11 Registrar: el envío del sacoAzul del centro de procesamiento liniers a la tintorería higa, el trabajo de la tintorería higa sobre el sacoAzul, el envío al cliente manliba de todos los uniformes listos | Hay que verificar: a) que el centro de procesamiento genere un envío con un uniforme listo (el sacoAzul), b) que el pantalonBlanco no debe formar parte del envío a manliba, c) que la tintorería higa no quede con uniformes pendientes, d) que el centro de procesamiento liniers tenga al pantalonBlanco como uniforme pendiente, e) que el centro de procesamiento liniers no tenga al sacoAzul como uniforme pendiente |


## Links

- [Volver a ejercicios introductorios](index.md)
