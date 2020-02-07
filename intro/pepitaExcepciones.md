
## Pepita (ahora con 100% más excepciones)

Pepita, la golondrina, ha sido modelada para poder volar y comer, y cuando eso sucede su energía disminuye y aumenta respectivamente. Ahora se agrega la necesidad de responder ante casos problemáticos:

1. Si come demasiado, superando una cantidad máxima de energía determinada, le duele el estómago y no puede continuar
2. Si se le pide que vuele más de lo que puede soportar por su energía actual, se queja y no vuela

Éste es el código propuesto:

```xtend
class Pepita {
  final static int MAX_ENERGIA = 120
  int energia = MAX_ENERGIA

  def void volar(Terreno terreno) {
    if (this.energia < terreno.superficie()) {
      throw new SinSuficienteEnergiaException(”No puedo volar: ” + terreno.superficie())
    }
    this.energia -= terreno.superficie()
  }

  public void comer(int cuanto) {
    this.energia += cuanto
    if (this.energia > MAX_ENERGIA) {
      throw new DolorDeEstomagoException()
    }
  }
}
```

Por otro lado tenemos lo siguiente para distintos tipos de terreno:

```xtend
class Terreno {
  def int superficie() { 100 }
}

public class Cancha extends Terreno {
  override superficie() { 20 }
}

public class Ciudad extends Terreno {
  override superficie() { 50 }
}
```

Antes de cada prueba, se corre:

```xtend
val pepita = new Pepita()
val terreno = new Terreno()
val cancha = new Cancha()
val ciudad = new Ciudad()
```

Los casos de prueba son:

```xtend
// 1
pepita.volar(ciudad)

// 2
pepita.volar(terreno)
pepita.volar(ciudad)
pepita.volar(cancha)

// 3 
pepita.volar(terreno)
pepita.comer(20)
pepita.comer(50)
pepita.comer(100)
pepita.comer(300)

// 4
pepita.volar(terreno)
pepita.comer(50)
try {
    pepita.comer(300)
    pepita.comer(500)
} catch(DolorDeEstomagoException e) {
    pepita.volar(cancha)
}
pepita.comer(10)
```

## Objetivos

Para cada linea de código de cada test, indique:

1. La energía de pepita antes de ejecutar la línea
2. Si la línea se ejecuta o no
3. La energía de pepita después de ejecutar la línea (si es que se ejecuta)

Para cada test, indique:

1. Si el test termina con excepción o termina en forma normal
2. En caso de terminar con excepción, indique qué tipo de excepción

## Links

- [Volver a ejercicios introductorios](index.md)
- Siguiente ejercicio: [Solicitudes de notebooks](solicitudesNotebooks.md)
