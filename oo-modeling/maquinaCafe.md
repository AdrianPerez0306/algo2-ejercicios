![maquina de cafe](/images/maquinaCafe.png)

## Máquina de Café

La cadena de cafeterías más importante a nivel mundial nos ha solicitado el desarrollo del front end de software para su próxima generación de máquinas de café que alquila o vende a oficinas. El software a desarrollar deberá proveer el armado de las bebidas, seleccionando los ingredientes de acuerdo con las opciones elegidas. Si no se dispone de los ingredientes necesarios, no se armará la bebida. El sistema de mezclado de café y provisión de ingredientes fue desarrollado por otra empresa, la cual nos ha proporcionado su interfaz:

```java
interface DispenserAutomatico { 

    public boolean tieneCafe(string tipo, float gramos)
    public boolean tieneLeche(TipoLeche tipo, int centilitros)
    public boolean tieneAzucar(float cucharadas)
    public boolean tieneEdulcorante(float cucharadasEquivalentes) //equivalente azucar,edulcorante 
    //... 

    public void ponerVaso(TamanioVaso tamanio)
    public void dispensarCafe(string tipo, float gramos)
    public void dispensarAgua(int onzas)
    public void dispensarLeche(TipoLeche tipo, int onzas)
    public void dispensarEspecia(int container, int onzas)
      // 0=chocolate, 
      // 1=canela, 
      // 2=componenteJamaiquino (sólo en las sucursales de Kingston y Amsterdam) 
    public void dispensarSyrup(int container, int medidas)
    public void dispensarAzucar(float cucharadas)
    public void dispensarEdulcorante(float cucharadasEquivalentes)
    //... 

    public void cancelar()

}
```

El departamento de diseño gráfico nos ha proporcionado un bosquejo del diseño de pantalla, a partir de la cual el cliente elegirá las opciones que desee para la elaboración del menú.

Ej: Elaboración de un Syrup Flavored Latte "Grande" con azúcar y Cacao:

- El usuario selecciona vaso "Grande", "Syrup flavored Latte", "Azúcar" (2 veces para extra azúcar) y hace clic en "iniciar"
- La máquina dispone un vaso grande en el receptáculo para vasos y arroja 4 medidas de Syrup en el vaso. También arroja el azúcar.
- La máquina comienza a la elaboración del brebaje, mezclando 2 gramos de café Brasil con 12 onzas de agua. Luego añade 4 onzas de leche descremada mientras va arrojando la mezcla al vaso, formando un exquisito degradé. La máquina agrega el cacao. Al finalizar emite un pitido.

Se pide:

- Diagramar las clases que componen el sistema, destacando las principales interacciones. Sólo debe diseñarse lo mínimo que responda a los requerimientos. 
- Codificar el método que a partir de la bebida predefinida y las modificaciones elabore la bebida. 
- Aclarar mediante código la implementación de cada método que considere necesario.
Codificar al menos 1 test por cada historia de usuario

### Historias de usuario:

- Crear un "White Chocolate Mocha" tamaño "Grande", con "Crema" y 2 cucharadas de "Azúcar". 
- Solicitar un "Caffé Latte", "Short", cuando no se disponga de granos de café. 
- Preparar un "Syrup Flavored Latte", "Venti", con "edulcorante" y cancelar el café antes de preparar la mezcla. 

### Notas

- Sólo se puede elaborar un pedido en simultáneo. Si se hace clic en vaso "Grande" y luego en "Venti", el café se hará en "venti". 
- Cada menú de los indicados arriba utiliza un único tipo de café. No hace falta modelar la mezcla de distintos tipos de granos de café. 
- No es necesario implementar todos los llamados a la interfaz, sólo los necesarios para cumplir con los requerimientos y comunicar la solución propuesta. 
- La empresa que elabora la pantalla nos ha indicado que los botones pulsados por el usuario serán recibidos mediante la llamada a un método llamado `pulsar(String botonPulsado)` que nosotros deberemos implementar. Ellos se encargarán de hacer que la máquina llame a dicho método. 
- Las bebidas provistas varían según la región y empresa que contrate el servicio. La configuración es realizada subiendo un archivo de configuración, cuya carga queda fuera del alcance del sistema. 
- El archivo de configuración indicará los ingredientes disponibles en la máquina, las recetas de café (líquidos, granos, jarabes y especias) y los agregados posibles por cada café 
- Los ingredientes de las bebidas son proporcionales de acuerdo al tamaño. Por ejemplo, para un café de 16 onzas se requieren 2 cucharadas de café mientras que para uno de 12 onzas se requieren 1.5 cucharadas.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
- Siguiente ejercicio: [Juego de la Vida](juegoVida.md)
