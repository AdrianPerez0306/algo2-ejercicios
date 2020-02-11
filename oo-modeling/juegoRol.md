## Juego de rol

### Contexto

Estamos haciendo un [MMORPG (Massive Multiplayer Online Role Playing Game)](http://en.wikipedia.org/wiki/Massively_multiplayer_online_role-playing_game).

En la etapa en que nos encontramos el único comportamiento que tienen los personajes (a partir de ahora PJs) es

- hacer un ataque con un arma,
- decirnos su defensa y
- saber el nombre de las armas que tienen habilitadas.

Apenas nace un PJ no tiene ningún oficio; cada ataque daña al oponente en base al daño que tenga el arma (todas las armas comienzan con un daño inicial de 10 puntos), su defensa está determinada para cada personaje y sólo tienen habilitada el arma "paloConClavoEnLaPunta" (cada arma se puede representar con un String o con un objeto Arma, esto es indistinto para la resolución del ejercicio).

Los oficios que se aprenden a lo largo del juego son:

### Mago

- Cuando atacan aumentan en 15 puntos el daño del arma
- Su defensa se reduce en 20 puntos pero nunca la deja en menos de 1.
- Se habilita el arma "staff"

### Paladín

- Cuando atacan aumentan en 5 el daño del arma
- Su defensa aumenta en 10 puntos
- Se habilita el arma "hacha" y el arma "espada"

### Clérigo

- Cuando atacan no pasa nada adicional
- Su defensa aumenta en 20 puntos
- Se habilita el arma "biblia"

A medida que uno juega con un PJ va ganando oficios.

Puede ganar más de un oficio pero nunca gana 2 veces el mismo oficio.

## Links

- [Volver a ejercicios de modelado con objetos](index.md)
