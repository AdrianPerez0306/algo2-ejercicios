
## Tareas

### Contexto

Una organización necesita que se implemente un sistema para hacer el seguimiento del desarrollo de tareas.

Cada tarea tiene una cantidad estimada de horas/hombres necesarias para ser terminada y un responsable y algunos empleados asignados, de los cuales se conoce cuánto cobran por hora trabajada. Las horas necesarias para finalizar una tarea son las horas/hombre que requiere divido la cantidad de empleados (sin contar al responsable el cual, claramente, no aporta nada para reducir este número)

El costo de una tarea es el costo de la infraestructura necesaria para llevarla a cabo más los salarios que les corresponden a cada uno de los empleados asignados por cada hora que tuvieron que trabajar. Consideramos que el responsable trabaja el total de las horas de la tarea porque somos unos babosos ingenuos.

O sea,

> Costo de Tarea = (Horas Hombre / Nro. de Empleados) * Sueldo por hora de Cada Empleado + Horas Hombre * Sueldo del Responsable + costo de infraestructura

Algunas tareas se consideran "de integración" y consisten, básicamente, en coordinar otras tareas. Estas tareas no tienen un costo propio por infraestructura y tardan tanto como la suma de lo que tardan sus subtareas mas una hora para reuniones de planificación por cada 8 horas de trabajo real.

Se considera que su costo es la suma de los costos de sus subtareas mas un bonus que se le paga al responsable, equivalente a 10% de su sueldo.

### Objetivos

1. Obtener las horas necesarias para finalizar una tarea
2. Obtener el costo de una tarea

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Cuentas contables](cuentasContables.md)
