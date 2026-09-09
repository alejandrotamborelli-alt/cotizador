# Cotizador

Calculadora de precios para servicios subcontratados. Una sola página HTML, sin dependencias.

**App:** https://alejandrotamborelli-alt.github.io/cotizador/

## Qué hace

**Precio final** — a partir del costo de subcontratar, el porcentaje del inversionista y el que querés que te quede, calcula cuánto cobrarle al cliente. Cada porcentaje puede ser *del total* o *de la ganancia*.

Los porcentajes sobre el total no se suman al costo: se despejan, porque son parte del precio que todavía no se conoce.

```
Precio = Costo × (1 − a·i − b·m) / (1 − i − m)
```

donde `i` y `m` son los porcentajes del inversionista y el propio, y `a`/`b` valen 1 si ese porcentaje se calcula sobre la ganancia y 0 si es sobre el total.

Con costo 800, inversionista 25% del total y 20% del total para uno: **1.454,55** (no 1.160).

Si los dos porcentajes son sobre la ganancia, el precio queda indefinido salvo que sumen 100%: la app lo avisa en vez de inventar un número.

**Cuánto me queda** — el camino inverso: con el precio final, el costo y el porcentaje del inversionista, dice cuánto te queda y qué porcentaje representa, tanto del total como de la ganancia.

## Detalles

- Los porcentajes y las opciones *del total / de la ganancia* se guardan en `localStorage` y vuelven la próxima vez. Los montos no: cambian en cada trabajo.
- Todo se calcula en el navegador. Nada se envía a ningún servidor.
