# DESIGN.md — kioshi (página personal, v5)

## Qué es
Portafolio y carta de servicios de Kioshi Shimabuku, diseñador gráfico y de
personajes en Lima. Una sola página, sin build, publicada en
`pop.llamicornios.com`.

## Modo y tipo
- **Modo de superficie:** Experience (la obra lidera) con cierre Persuade
  (contacto). La interfaz se retira: nada compite con las piezas.
- **Tipo de negocio:** `service` — se contrata a una persona. Fotografía del
  trabajo real, color plano, tipografía, cero efectos.
- **Acción principal:** escribir por WhatsApp con el motivo ya escrito.
- **Primer pantallazo:** quién es, qué hace y una prueba (pieza + 40 expos).

## Referencias
- `hectorhuaman.com` — ritmo editorial peruano, fotografía sin adornos.
- `mikemontgomery.design/work/art-toy` — cómo se presenta un toy designer.
- `anagrama.com` — contención tipográfica y grillas asimétricas.

## Tipografía
- Display: **Hijos del Sol** Regular (auto-hospedada, woff2 8 KB). Único peso:
  la jerarquía se hace con tamaño, caja y tracking, no con negritas.
- Body: **Source Code Pro** 400 / 600 (auto-hospedada, 21 KB cada una).
- Escala: 13 / 14 / 16 / 20 / 28 / 40 / 64 → seis visibles por página.
- `line-height` 1.12 en display (las tildes de Hijos del Sol son bloques
  pesados), 1.75 en body. Medida de párrafo 62–70 ch.
- Prohibido: una tercera familia, Google Fonts, pesos sintéticos.

## Color (hex exactos)
- `--paper` #FFF6E9 (fondo)
- `--ink` #121110 (texto)
- `--ink-soft` #4A443D (secundario)
- `--red` #B32B22 (acento único: CTA, bandas, foco)
- `--yellow` #F5B302 (solo bloques de énfasis, nunca texto)
- `--teal` #0E8F8F (solo un bloque, nunca texto pequeño)
- Prohibido: degradados, índigo/violeta, glass, texto con gradiente.

## Geometría
- Retícula de 12 columnas, `max-width: 1200px`, gutter fluido.
- Espaciado: 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96.
- Radio: 0 en todo (mundo neobrutalista documentado; las sombras duras son
  sistema, no disfraz — excepción deliberada a la regla de impeccable).
- Bordes: 3 px `--ink` en marcos, botones y bandas.

## Motion
- **Un solo momento autoral:** entrada del hero (opacidad + 12 px, 520 ms,
  `cubic-bezier(.23,1,.32,1)`, escalonado 60 ms). Nada más entra al scroll.
- Hover: pieza sube 2 px y su imagen escala 1.02 dentro del marco (180 ms).
  Subrayado de nav con `scaleX` (no `width`).
- Press: `translate(2px,2px)` sin sombra (100 ms).
- `prefers-reduced-motion`: sin animación, contenido visible.
- Gate: `@media (hover:hover) and (pointer:fine)`.

## Superficies del navegador
- `::selection` amarillo con tinta.
- `caret-color: var(--red)`.
- `scrollbar-color: var(--red) var(--paper)`, ancho thin.
- `:focus-visible`: anillo de 3 px rojo con offset 3 px.

## Contenido
- Solo hechos del CV y del portafolio. Cero testimonios, cifras o clientes
  inventados.
- Cada cifra aparece una vez. "+40 exposiciones" solo en Sobre mí.
- Fotos: las 9 reales del proyecto; ninguna repetida entre secciones.

## Banned list
- Kicker sobre el h1 y números de sección decorativos (01–08).
- Degradados, glass, `border-left` de color, sombras difusas genéricas.
- Emoji como icono; monoespaciada como disfraz.
- Reveals por scroll y contenido con `opacity:0` por defecto.
