# Cotizador

Calculadora de precios para servicios subcontratados. Una sola página HTML, sin dependencias.

**App:** https://alejandrotamborelli-alt.github.io/cotizador/

## Qué hace

**Precio final** — a partir del costo de subcontratar, el porcentaje del inversionista y el de PYB, calcula cuánto cobrarle al cliente. Los dos porcentajes son sobre el total.

Un porcentaje del total no se suma al costo: hay que despejarlo, porque se aplica sobre el precio que todavía no se conoce.

```
Precio = Costo / (1 − inversionista − PYB)
```

Con costo 800, inversionista 25% y PYB 20%: **1.454,55** (no 1.160).

Si los porcentajes suman 100% o más no hay precio posible, y la app lo avisa en vez de mostrar un número imposible.

**Cuánto me queda** — el camino inverso: con el precio final, el costo y el porcentaje del inversionista, dice cuánto le queda a PYB y qué porcentaje del total representa.

Las dos pantallas muestran el reparto completo (subcontratación, inversionista, PYB) y la mitad de lo de PYB.

## Detalles

- Los porcentajes se guardan en `localStorage` y vuelven la próxima vez. Los montos no: cambian en cada trabajo.
- Todo se calcula en el navegador. Nada se envía a ningún servidor.
