# Prompts de imágenes para la web (Nano Banana / Gemini)

Las páginas YA funcionan con arte provisional sacado del juego. Cuando tengas las imágenes nuevas, **guárdalas con el nombre exacto** en `assets/img/` (sobrescriben a las provisionales) y no hace falta tocar el HTML. Mantén el peso por debajo de 300 KB (webp calidad ~80; el og-image en jpg).

Estilo común (ya va dentro de cada prompt): juguete de arcilla 3D tipo Royal Match / Clash Royale, siluetas simples y gruesas, colores saturados, sombreado suave, **sin texto dentro de la imagen** y sin marcas de agua.

Imágenes de referencia (adjuntar siempre las que se indican): `esquiador_hombre.jpg`, `esquiador_mujer.jpg` y `yeti.jpg`, en `C:\Users\jonathan\Desarrollo\sno-way-out\modelos imágenes\`.

Prioridad: **1 (la más importante) = hero.webp**, 2 = og-image.jpg, 3 = reto-banner.webp.

---

## 1. Héroe de la landing — `hero.webp` (PRIORIDAD ALTA)

- Dónde se usa: bajo el logo en `index.html` y `en/index.html` (recuadro redondeado, `object-fit: cover`).
- Tamaño: 2048 x 1024 px, relación 2:1. Dejar el centro despejado de texto; sin logo (el logo ya está en la página).
- Referencias a adjuntar: `esquiador_hombre.jpg`, `yeti.jpg` (opcional `esquiador_mujer.jpg`).
- Provisional actual: recorte del feature graphic (lleva el logo dibujado; la nueva no debe llevarlo).

```
Wide 2:1 key art for a mobile skiing game. The skier from the first reference image (red ski suit, goggles, yellow skis) races diagonally down a snowy mountain slope toward the camera, a big joyful grin, one pole raised. Right behind him the furry white-and-lavender yeti from the second reference image chases him with arms stretched out, mouth open, kicking up snow. A husky dog in a small red scarf runs alongside, a few shiny gold coins float in the air, snow-covered pine trees on both sides, bright sky-blue background with fluffy clouds. 3D clay toy style like Royal Match and Clash Royale, bold simple thick silhouettes, bright saturated colors, very soft shading, no fine texture. Keep the characters in the center two-thirds of the frame with the top and bottom edges free of important details. No text, no logo, no watermark.
```

## 2. Imagen para compartir en redes — `og-image.jpg`

- Dónde se usa: `og:image` y `twitter:card` de las páginas de inicio (cuando alguien comparte el enlace en WhatsApp, Telegram, etc.).
- Tamaño: 1200 x 630 px, relación 1.91:1 (JPG).
- Referencias: `esquiador_hombre.jpg`, `yeti.jpg`.
- Nota: aquí SÍ conviene el logo; si Nano Banana no lo hace bien, genérala sin texto y yo la compongo con `game/icons/ui/title.png`. Pide la escena con un hueco limpio arriba o a la izquierda para colocar el logo.
- Provisional actual: recorte centrado del feature graphic.

```
Wide 1.91:1 social sharing image for a mobile skiing game. Left third: clean pale-blue sky with soft clouds and empty space (a logo will be added there later). Right two-thirds: the skier from the first reference image (red ski suit) skiing fast down a snowy slope, looking back in panic at the furry white-and-lavender yeti from the second reference image diving after him. Snowy pine trees, sparkling snow spray, a few gold coins. 3D clay toy style like Royal Match and Clash Royale, bold simple thick silhouettes, bright saturated colors, very soft shading. No text, no watermark.
```

## 3. Banner de la página de reto — `reto-banner.webp`

- Dónde se usa: parte superior de la tarjeta de `reto.html` (el enlace que se comparte para retar a un amigo).
- Tamaño: 1680 x 960 px, relación 7:4.
- Referencias: `esquiador_hombre.jpg`, `esquiador_mujer.jpg`.
- Provisional actual: recorte del feature graphic (esquiador + yeti).

```
7:4 illustration of a friendly head-to-head ski challenge. Two skiers side by side racing down the same snowy slope: the man from the first reference image in a red suit and the woman from the second reference image in a blue suit, each looking toward the viewer with a competitive smile, one making a "come and get me" gesture. A small furry yeti peeks out from behind a snowy pine tree in the background, gold coins along the track, a checkered finish flag far ahead, bright sky-blue background. 3D clay toy style like Royal Match and Clash Royale, bold simple thick silhouettes, bright saturated colors, very soft shading. No text, no watermark.
```

---

### Cómo quedan cableadas las rutas

| Archivo final | Referencia en HTML |
|---|---|
| `assets/img/hero.webp` | `index.html`, `en/index.html` (`<img src="assets/img/hero.webp">`, contenedor 2:1) |
| `assets/img/og-image.jpg` | `<meta property="og:image">` en landings (URL absoluta bajo `https://jdragneel3.github.io/sno-way-out-web/`) |
| `assets/img/reto-banner.webp` | `reto.html` (contenedor 7:4, `object-fit: cover`) |

Si las dimensiones cambian algo, no se rompe nada: los contenedores recortan con `object-fit: cover`.
