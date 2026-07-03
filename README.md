# Innovation Strategy Framework — Propuesta interactiva

Deck-propuesta técnico-comercial de **OmniSys** para la dirección de **Tiendas Garcés**.
Presentación web interactiva de 11 secciones con navegación por teclado, deep-dives
(pop-ups de detalle), barra de progreso, escalado responsivo y un contador de inversión animado.

**Una sola página, sin dependencias, sin build.** Es un `index.html` autónomo con un runtime
propio en JavaScript vanilla (~230 líneas) — solo carga tipografías desde Google Fonts.

## Estructura

```
.
├── index.html          # La aplicación completa (markup + estilos + runtime)
├── assets/img/         # Banco de imágenes del proyecto (el deck usa 9; el resto queda disponible)
├── design-source/      # Fuente de diseño (referencia, no se sirve)
│   ├── prototype.dc.html   # Prototipo original de Claude Design (<x-dc>/DCLogic)
│   ├── support.js          # Runtime del prototipo
│   ├── CONTENIDO.md        # Contenido/copys de la propuesta
│   └── HANDOFF.md          # Notas del handoff de diseño
└── README.md
```

`index.html` es una reimplementación fiel del prototipo `design-source/prototype.dc.html`,
reconstruida como código real y desplegable (se eliminó la dependencia del runtime del prototipo).

## Uso local

Como es un sitio estático, cualquier servidor HTTP sirve. Por ejemplo:

```bash
python3 -m http.server 4599
# abre http://localhost:4599/index.html
```

> Abrir el archivo con `file://` directamente también funciona, salvo por las
> tipografías remotas; se recomienda servirlo por HTTP.

## Controles

| Acción | Cómo |
|---|---|
| Avanzar / retroceder | flechas `←` `→`, `espacio`, `PageUp` / `PageDown`, o los controles del pie |
| Ir a una sección | clic en los puntos de navegación |
| Abrir un detalle | clic en cualquier tarjeta o nodo interactivo |
| Navegar entre detalles | flechas `←` `→` con un detalle abierto |
| Cerrar un detalle | `Esc`, el botón "Volver", o clic fuera |

## Despliegue

Al ser estático se publica en cualquier hosting (GitHub Pages, Vercel, Netlify, etc.).

- **GitHub Pages**: `Settings → Pages → Deploy from branch → main / root`.
- **Vercel / Netlify**: importar el repo; sin comando de build, output = raíz.

## Notas

- Diseñado sobre un lienzo fijo de 1280×720 que se escala para encajar en la ventana
  (comportamiento de deck de presentación). Ver *responsive* en el critique del proyecto.
- Confidencial — material comercial.
