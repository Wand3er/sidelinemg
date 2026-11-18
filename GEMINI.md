# SIDELINE — Athlete Brand Agency (Reglas del Proyecto y Contexto de Negocio)

## 1. Identidad de la Agencia
- **Nombre Comercial:** SIDELINE (`Sideline Sports Marketing` / `Sideline Agency`)
- **Tagline Oficial:** *Building Athletes Into Scalable Brands.*
- **Fundación:** Est. 2025
- **Ubicación:** Calle Hatuey 52A, Los Cacicazgos, Distrito Nacional, Santo Domingo, República Dominicana.
- **Sitio Web Oficial:** https://sidelinemg.com/ (desplegado automáticamente en Vercel desde la rama `main` de `https://github.com/Wand3er/sidelinemg.git`).
- **Teléfono Oficina:** +1 (809) 590-6325
- **Correos Corporativos:** `admin@sidelinemg.com` (visible en web) / `sebastian@sidelinemg.com` (recepción de formulario FormSubmit).
- **Leadership / Socios (`#team`):**
  1. **Darling José** — *Founder & Brand Director*
  2. **Marco Cabrera** — *Head of Partnerships & Strategy*
  3. **Sebastián Mañón** — *Head of Content & Digital*

## 2. Servicios de la Agencia (`#services`)
1. **01 Brand Strategy:** Definición de identidad y base estratégica (valores, voz y posicionamiento).
2. **02 Content Production:** Producción cinematográfica de video, fotografía editorial y campañas comerciales listas para lanzamiento inmediato.
3. **03 Brand Roadmap:** Hojas de ruta de marca a largo plazo que evolucionan con la carrera del atleta dentro y fuera del terreno.
4. **04 Campaign Sourcing:** Identificación de patrocinios estratégicos y soporte creativo/productivo de extremo a extremo.
5. **05 Media & PR:** Dirección en momentos mediáticos, entrevistas y apariciones públicas.
6. **06 Hybrid Model:** Captura y entrega continua de contenido todo el año, tanto en el estadio como mediante producción remota.

## 3. Roster Oficial y Arquitectura MLB Stats API (`#roster`)
Cada tarjeta del Roster incluye su `data-mlb-id` oficial verificado contra `https://statsapi.mlb.com/api/v1/people/{id}`:
1. **Junior Caminero** (`data-mlb-id="691406"`) — Tampa Bay Rays · 3B (`assets/images/roster-caminero.webp`)
2. **Willy Adames** (`data-mlb-id="642715"`) — San Francisco Giants · SS (`assets/images/roster-adames.webp`)
3. **Agustín Ramírez** (`data-mlb-id="682663"`) — Miami Marlins · C (`assets/images/roster-agustin-ramirez.webp`)
4. **Marcell Ozuna** (`data-mlb-id="542303"`) — Pittsburgh Pirates · DH (`assets/images/roster-ozuna.webp`)
5. **Angel Genao** (`data-mlb-id="694197"`) — Cleveland Guardians · INF (`assets/images/roster-angel-genao.webp`)
6. **Geraldo Perdomo** (`data-mlb-id="672695"`) — Arizona Diamondbacks · SS (`assets/images/roster-perdomo.webp`)
7. **Heliot Ramos** (`data-mlb-id="671218"`) — San Francisco Giants · OF (`assets/images/roster-ramos.webp`)
8. **Christopher Morel** (`data-mlb-id="666624"`) — Miami Marlins · LF (`assets/images/roster-christopher-morel.webp`)
9. **Jesús Made** (`data-mlb-id="815908"`) — Milwaukee Brewers · SS (`assets/images/roster-jesus-made.webp`)

### Reglas del Modal de Estadísticas (`#mlbModal`)
- **Soporte MLB + MiLB:** La consulta a `statsapi.mlb.com` hidrata tanto Grandes Ligas (`sportId=1`) como Ligas Menores (`sportIds=11,12,13,14,16`). Si un jugador ya debutó en MLB, muestra sus últimas 3 temporadas MLB + fila `CAREER`; si es prospecto activo en MiLB, muestra automáticamente sus temporadas de Ligas Menores con la etiqueta del nivel (`AAA`, `AA`, `A+`, `A`, `ROK`) y fila `MILB CAREER`.
- **Headshot resiliente:** Se utiliza `https://img.mlbstatic.com/mlb-photos/image/upload/w_240,q_auto:best/v1/people/${mlbId}/headshot/67/current` con fallback automático (`onerror`) a la fotografía oficial local del atleta en `assets/images/roster-*.webp`.

## 4. Sistema de Diseño y Estética Web
- **Paleta Oficial:**
  - Brand Orange (`--brand-orange`): `#fc7315`
  - Black (`--black`): `#0A0A0A`
  - Graphite (`--graphite`): `#1E1E1E`
  - Light Graphite (`--light-graphite`): `#2A2A2A`
  - Off-White (`--white`): `#F5F3EF`
  - Gray (`--gray`): `#8A8A8A`
  - Light Gray (`--light-gray`): `#E8E6E2`
- **Tipografías:** `Bebas Neue` (titulares display), `Cormorant Garamond` (citas e itálicas editoriales) y `DM Sans` (cuerpo de texto y etiquetas UI).
- **Activos Locales:** Todas las imágenes deben servirse en formato `.webp` desde `assets/images/` con caché inmutable en `vercel.json`. Prohibido usar enlaces externos de `postimg.cc`.

## 5. Directivas de Ejecución del Agente
- **Acción Directa:** Al realizar mejoras o cambios solicitados por el usuario, valida el HTML/CSS/JS, optimiza cualquier imagen nueva a `.webp` en `assets/images/` y ejecuta `git commit` + `git push origin main` para actualizar el despliegue en Vercel.
