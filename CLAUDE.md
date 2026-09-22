# Web personal — Rodrigo Lazaroff

Portfolio de una sola página: presentación, grilla de proyectos con filtros por
categoría, formación y contacto. Sin build ni dependencias: es un `index.html`
con todo el CSS y el JS embebidos, más `assets/`.

## Stack

HTML + CSS + JS vanilla, sin dependencias. Deploy en Vercel (sitio estático).

## Diseño

Minimalismo editorial: fondo hueso, monocromo cálido, una sola familia de
acentos en pasteles lavados (uno por categoría de proyecto). Nada de gradientes
llamativos, neón, sombras marcadas ni cursores custom.

- **Tipografía**: Instrument Serif para los títulos (con itálica como único
  énfasis), Geist para el cuerpo, Geist Mono para metadatos y rótulos.
- **Color**: todo sale de las variables de `:root`. Los grises `--muted` y
  `--faint` están calibrados a 6.0:1 y 4.8:1 sobre el fondo — si se aclaran, la
  tipografía chica deja de pasar WCAG AA.
- **Bordes y radios**: `1px solid var(--line)`, radio 10px en tarjetas y 6px en
  botones. Las sombras solo aparecen en hover y apenas se ven.
- **Movimiento**: entrada por scroll con IntersectionObserver (fade + 12px),
  escalonada con `--i` en cada elemento. Todo respeta `prefers-reduced-motion`.

## Cómo se levanta

```bash
npx serve -l 5500 .
```

Queda en http://localhost:5500. También sirve abrir `index.html` directo, pero
el server evita problemas con rutas de `assets/`.

## Cómo se deployea

Push a `main` → Vercel publica solo. Es estático: sin build command, output
directory `.`.

## Proyectos de la grilla

Cada tarjeta vive en `#projects` con su `data-cat`. Si el proyecto está
publicado es un `<a class="card">` que abre el sitio en pestaña nueva y cierra
con `<span class="go">`; si todavía no, es un `<div class="card">` que cierra
con `<span class="soon">` y no enlaza a ningún lado.

Los filtros y sus contadores se generan por JS a partir de las tarjetas, así
que agregar una no obliga a tocar nada más. Lo único manual es el número de
orden (`<span class="idx">`).

| Tarjeta | Link |
|---|---|
| Dr. Mauricio Benetti | https://neurologomauriciobenetti.vercel.app |
| Barra Pesquera BNA | pendiente (sin deploy conocido) |
| Ciudadanía Búlgara | https://ciudadaniabulgara.com.ar |
| Rentify | pendiente (Rentifay es single-tenant: datos en una Sheet propia) |
| Canchita | https://canchita-sigma.vercel.app |
| Paga Mejor | https://paga-mejor.vercel.app |
| ¿Un día más, o un día menos? | https://undiamas-o-undiamenos.vercel.app |
| Simulador de Préstamos Pro | https://simulador-financiero-pro.lovable.app |
| BiVi | https://bivipaginaweb.vercel.app |
| Dra. Lucia Nosetti | https://dermatologalucianosetti.vercel.app |
| Divisor de Gastos | pendiente (falta deploy y cuentas por usuario) |

Canchita, BiVi y Dra. Lucia Nosetti aparecen además en «Seleccionados», el
bloque del hero. Esa lista está escrita a mano: si cambia, se edita ahí.

La sección Contacto tiene botones a email (rodrigolazaroff@gmail.com),
WhatsApp (+543777659236, con mensaje precargado), Instagram
(@rodrigolazaroff) y LinkedIn (in/rodrigolazaroff).
