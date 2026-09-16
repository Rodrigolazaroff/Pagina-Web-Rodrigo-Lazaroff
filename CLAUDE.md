# Web personal — Rodrigo Lazaroff

Portfolio de una sola página: presentación, grilla de proyectos con filtros por
categoría, formación y contacto. Sin build ni dependencias: es un `index.html`
con todo el CSS y el JS embebidos, más `assets/`.

## Stack

HTML + CSS + JS vanilla. Fuentes de Google (Orbitron, Inter, JetBrains Mono).
Animaciones y cursor custom hechos a mano. Deploy en Vercel (sitio estático).

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

Cada tarjeta es un `<a class="card">` dentro de `#projects`, con `data-cat` para
el filtro. El link va al sitio en producción del proyecto, en pestaña nueva.

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

Al contar tarjetas, actualizar también los números de los filtros (`.count`) y
el `P_0x` de cada tarjeta.
