# Asteroids

Clon del clásico arcade **Asteroids** implementado en canvas HTML5 puro, sin dependencias ni bundler.

## Descripción

Nave espacial en un campo de asteroides con envolvimiento de bordes (el espacio es toroidal). Destruye asteroides para sumar puntos: los grandes se parten en medianos, los medianos en pequeños. Incluye power-ups especiales y tipos de asteroides únicos como la estrella fugaz.

## Tecnologías

- **HTML5 Canvas** — renderizado 2D
- **JavaScript (ES6+)** — lógica del juego en un solo archivo `game.js`
- Sin frameworks, sin bundler, sin dependencias

## Cómo correr

Abre `index.html` directamente en el navegador (doble clic), o usa un servidor local:

```bash
npx serve .
```

Luego visita `http://localhost:3000`.

## Controles

| Tecla     | Acción     |
| --------- | ---------- |
| `←` `→`   | Rotar nave |
| `↑`       | Propulsar  |
| `Espacio` | Disparar   |

## Puntuación

| Asteroide        | Puntos |
| ---------------- | ------ |
| Grande           | 20     |
| Mediano          | 50     |
| Pequeño          | 100    |
| Estrella fugaz (grande) | 100 |
| Estrella fugaz (pequeña) | 150 |

## Características

- 3 vidas con invencibilidad temporal al reaparecer (parpadeo)
- Asteroides se parten en fragmentos más pequeños al ser destruidos
- Partículas de explosión al destruir asteroides
- Power-up **Velocidad**: algunos asteroides sueltan un rayo ⚡ que duplica el empuje de la nave durante 5 segundos (se acumula al recoger varios)
- Power-up **Triple**: algunos asteroides sueltan tres puntos 🔺 que disparan 3 balas en abanico durante 5 segundos (se acumula al recoger varios)
- Power-up **Escudo**: icono cian que dura 8 segundos; mientras está activo la burbuja alrededor de la nave destruye cualquier asteroide (incluidas las fugaces) que la toque, sumando sus puntos y consumiendo 2 s de escudo por impacto (se acumula al recoger varios)
- **Estrella fugaz**: aparece cada 8-15 s, mucho más rápida que un asteroide normal y dorada con estela; desaparece sola tras unos segundos (se desvanece y parpadea). Al destruirla da 100 pts y se parte en 2 fugaces pequeñas de 150 pts cada una. Chocar con ella mata a la nave
