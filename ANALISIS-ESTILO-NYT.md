# Análisis de Estilo: The New York Times

**Fecha:** 2025-01-19
**Publicación:** The New York Times (Artículos digitales)
**Basado en:** Estándares de diseño NYT 2024-2025

---

## 1. TIPOGRAFÍA

### Fuentes principales

| Elemento | Fuente | Tamaño | Peso | Line Height |
|:---------|:-------|:-------|:-----|:------------|
| **Título principal (H1)** | Cheltenham, Georgia | 2.625rem (42px) | 700 (Bold) | 1.2 |
| **Subtítulo (H2)** | Cheltenham, Georgia | 2rem (32px) | 700 (Bold) | 1.3 |
| **Subsección (H3)** | Cheltenham, Georgia | 1.5rem (24px) | 700 (Bold) | 1.4 |
| **H4** | Franklin Gothic, sans-serif | 1.25rem (20px) | 600 (Semibold) | 1.4 |
| **Cuerpo de texto** | Georgia, serif | 1.125rem (18px) | 400 (Regular) | 1.625 |
| **Subtexto/Captions** | Franklin Gothic, sans-serif | 0.875rem (14px) | 400 (Regular) | 1.5 |
| **Byline/Metadatos** | Franklin Gothic, sans-serif | 0.9375rem (15px) | 400 (Regular) | 1.4 |
| **Labels/Tags** | Franklin Gothic, sans-serif | 0.75rem (12px) | 600 (Semibold) | 1.3 |

### Familias de fuentes

```css
/* Títulos principales */
font-family: Cheltenham, Georgia, 'Times New Roman', serif;

/* Cuerpo de artículos */
font-family: Georgia, 'Times New Roman', serif;

/* Subtítulos, captions, UI */
font-family: 'Franklin Gothic', 'Helvetica Neue', Helvetica, Arial, sans-serif;

/* Sistema (fallback) */
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

### Características tipográficas

- **Line-height cuerpo:** 1.625 (lectura cómoda)
- **Line-height títulos:** 1.2 - 1.4 (ajustado)
- **Font-smoothing:** `-webkit-font-smoothing: antialiased`
- **Letter-spacing:** Normal en cuerpo, ligeramente reducido en títulos grandes
- **Contrast:** Alto contraste entre títulos (bold) y cuerpo (regular)

---

## 2. PALETA DE COLORES

### Colores principales

| Uso | Hex Code | RGB | Descripción |
|:----|:---------|:----|:------------|
| **Fondo página** | `#FFFFFF` | 255,255,255 | Blanco puro |
| **Texto principal** | `#121212` | 18,18,18 | Negro profundo |
| **Texto secundario** | `#363636` | 54,54,54 | Gris oscuro |
| **Enlaces** | `#326891` | 50,104,145 | Azul NYT clásico |
| **Enlaces hover** | `#121212` | 18,18,18 | Negro al hover |
| **Bordes** | `#DFDFDF` | 223,223,223 | Gris claro |
| **Líneas divisorias** | `#E2E2E2` | 226,226,226 | Gris muy claro |

### Colores de marca NYT

| Elemento | Hex Code | RGB | Uso |
|:---------|:---------|:----|:----|
| **NYT Black** | `#000000` | 0,0,0 | Logo, headers importantes |
| **NYT Blue** | `#326891` | 50,104,145 | Enlaces, elementos interactivos |
| **NYT Gray** | `#666666` | 102,102,102 | Metadatos, subtexto |
| **Byline Gray** | `#727272` | 114,114,114 | Nombres de autores |
| **Date Gray** | `#696969` | 105,105,105 | Fechas de publicación |

### Colores de acento

| Elemento | Hex Code | RGB | Uso |
|:---------|:---------|:----|:----|
| **Breaking News** | `#D0021B` | 208,2,27 | Alertas, noticias urgentes |
| **Opinion Yellow** | `#F4D555` | 244,213,85 | Sección de opinión |
| **Highlight** | `#FFF1C2` | 255,241,194 | Texto resaltado |
| **Success** | `#2E7D32` | 46,125,50 | Mensajes positivos |
| **Background Alt** | `#F7F7F7` | 247,247,247 | Fondos alternativos |

---

## 3. ESTRUCTURA Y ORGANIZACIÓN

### Layout principal

```
┌────────────────────────────────────────────────────┐
│              HEADER (Negro con logo)               │
├────────────────────────────────────────────────────┤
│                                                    │
│  ┌──────────────────────┐  ┌──────────────────┐   │
│  │                      │  │                  │   │
│  │    ARTÍCULO MAIN     │  │    SIDEBAR       │   │
│  │    (66.67%)          │  │    (33.33%)      │   │
│  │                      │  │                  │   │
│  │  - Título            │  │  - Related       │   │
│  │  - Byline            │  │  - Most Popular  │   │
│  │  - Fecha             │  │  - Ads           │   │
│  │  - Contenido         │  │                  │   │
│  │                      │  │                  │   │
│  └──────────────────────┘  └──────────────────┘   │
│                                                    │
└────────────────────────────────────────────────────┘
```

### Proporciones

- **Contenedor máximo:** 1280px - 1440px
- **Columna principal:** 600px - 720px (artículos estándar)
- **Márgenes laterales:** Mínimo 20px (móvil), 40px (desktop)
- **Sidebar:** 300px - 360px
- **Gap entre columnas:** 40px - 60px

### Márgenes y espaciado

| Elemento | Valor |
|:---------|:------|
| **Contenedor máximo** | 1280px |
| **Padding contenedor** | 20px (móvil), 40px (desktop) |
| **Margen entre párrafos** | 20px |
| **Margen entre secciones** | 40px - 60px |
| **Espaciado en listas** | 12px entre items |
| **Espaciado H2-contenido** | 24px |
| **Espaciado título-byline** | 16px |

---

## 4. CAJAS INFORMATIVAS Y CALLOUTS

### Estilos de cajas NYT

#### Caja estándar (Editor's Note / Context Box)

```css
background-color: #F7F7F7;
border-left: 3px solid #121212;
padding: 20px;
margin: 32px 0;
font-size: 0.9375rem;
line-height: 1.6;
```

#### Caja de opinión

```css
background-color: #FFF9E6;
border-top: 2px solid #F4D555;
border-bottom: 2px solid #F4D555;
padding: 24px;
margin: 32px 0;
```

#### Breaking News Banner

```css
background-color: #D0021B;
color: #FFFFFF;
padding: 12px 20px;
font-size: 0.875rem;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.5px;
```

#### Summary Box / Key Points

```css
background-color: #FFFFFF;
border: 1px solid #DFDFDF;
border-top: 4px solid #326891;
padding: 24px;
margin: 32px 0;
```

---

## 5. ELEMENTOS VISUALES

### Byline (Autor)

```css
font-family: Franklin Gothic, sans-serif;
font-size: 0.9375rem;
color: #727272;
text-transform: uppercase;
letter-spacing: 0.5px;
font-weight: 600;
```

### Fecha de publicación

```css
font-family: Franklin Gothic, sans-serif;
font-size: 0.875rem;
color: #696969;
margin-top: 8px;
```

### Separadores

- **Grosor:** 1px para divisiones sutiles
- **Color:** `#E2E2E2`
- **Estilo:** Sólido
- **Márgenes:** 40px arriba y abajo

### Enlaces

```css
color: #326891;
text-decoration: underline;
text-underline-offset: 2px;
transition: color 0.15s ease;
```

```css
/* Hover */
color: #121212;
text-decoration: underline;
```

### Blockquotes (Citas destacadas)

```css
border-left: 3px solid #DFDFDF;
padding-left: 24px;
margin: 32px 0;
font-size: 1.25rem;
line-height: 1.5;
font-style: italic;
color: #363636;
```

---

## 6. FIGURAS Y TABLAS

### Figuras

#### Container

```css
margin: 40px 0;
width: 100%;
```

#### Imagen

```css
width: 100%;
height: auto;
display: block;
```

#### Caption (Pie de foto)

```css
font-family: Franklin Gothic, sans-serif;
font-size: 0.875rem;
line-height: 1.5;
color: #666666;
margin-top: 12px;
padding-top: 12px;
border-top: 1px solid #E2E2E2;
```

#### Crédito de foto

```css
font-size: 0.75rem;
color: #999999;
margin-top: 4px;
```

### Tablas

```css
border-collapse: collapse;
width: 100%;
margin: 32px 0;
font-family: Franklin Gothic, sans-serif;
font-size: 0.875rem;
```

#### Celdas

```css
border-bottom: 1px solid #E2E2E2;
padding: 12px 16px;
text-align: left;
```

#### Encabezados

```css
background-color: #F7F7F7;
font-weight: 700;
text-transform: uppercase;
font-size: 0.75rem;
letter-spacing: 0.5px;
color: #121212;
border-bottom: 2px solid #121212;
```

---

## 7. ELEMENTOS INTERACTIVOS

### Botones primarios

```css
background-color: #326891;
border: none;
border-radius: 2px;
color: #FFFFFF;
padding: 12px 24px;
font-family: Franklin Gothic, sans-serif;
font-size: 0.875rem;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 0.5px;
cursor: pointer;
transition: background-color 0.2s ease;
```

#### Hover state

```css
background-color: #244966;
```

### Botones secundarios

```css
background-color: #FFFFFF;
border: 1px solid #121212;
color: #121212;
padding: 12px 24px;
font-weight: 600;
```

### Tags / Labels

```css
background-color: #F7F7F7;
border: 1px solid #DFDFDF;
padding: 4px 12px;
font-size: 0.75rem;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 0.5px;
border-radius: 2px;
color: #666666;
```

---

## 8. ARTÍCULOS INTERACTIVOS / VISUALIZACIÓN DE DATOS

### Gráficos y visualizaciones

- **Colores principales:** Azul NYT (`#326891`), tonos complementarios
- **Grid lines:** `#E2E2E2` con stroke de 1px
- **Labels:** Franklin Gothic, 0.75rem, color `#666666`
- **Tooltips:** Fondo blanco, borde `#DFDFDF`, sombra sutil

### Scrollytelling elements

```css
position: sticky;
top: 80px;
background-color: rgba(255, 255, 255, 0.95);
backdrop-filter: blur(8px);
```

---

## 9. RESPONSIVE DESIGN

### Breakpoints

| Tamaño | Ancho | Cambios |
|:-------|:------|:--------|
| **Mobile S** | < 375px | Fuentes reducidas, padding mínimo |
| **Mobile M** | 375px - 599px | Layout single column, imágenes full width |
| **Tablet** | 600px - 1023px | Sidebar desaparece o se mueve abajo |
| **Desktop S** | 1024px - 1279px | Layout de 2 columnas estándar |
| **Desktop L** | ≥ 1280px | Layout completo con sidebar fijo |

### Ajustes por tamaño

#### Móvil (< 600px)

- Sidebar desaparece
- Fuentes reducidas 10%
- Padding: 20px
- Imágenes: 100% width
- Tablas: Scroll horizontal

#### Tablet (600px - 1023px)

- Sidebar al final del artículo
- Contenedor: 90% width
- Márgenes laterales: 5%

#### Desktop (≥ 1024px)

- Layout de 2 columnas
- Sidebar sticky
- Contenedor centrado max-width

---

## 10. SECCIÓN DE RESUMEN / ABSTRACT

### Estilo visual NYT

```css
background-color: #F7F7F7;
border-top: 3px solid #121212;
padding: 24px;
margin: 32px 0;
```

### Título de resumen

```css
font-family: Cheltenham, Georgia, serif;
font-size: 1.25rem;
font-weight: 700;
color: #121212;
margin-bottom: 16px;
text-transform: uppercase;
letter-spacing: 0.5px;
```

### Contenido

```css
font-family: Georgia, serif;
font-size: 1rem;
line-height: 1.6;
color: #363636;
```

---

## 11. METADATOS DEL ARTÍCULO

### Información del autor (Byline)

```css
display: flex;
align-items: center;
margin: 24px 0;
padding: 16px 0;
border-top: 1px solid #E2E2E2;
border-bottom: 1px solid #E2E2E2;
```

#### Nombre

```css
font-family: Franklin Gothic, sans-serif;
font-size: 0.9375rem;
font-weight: 600;
color: #121212;
text-transform: uppercase;
letter-spacing: 0.5px;
```

#### Rol/Título

```css
font-size: 0.875rem;
color: #666666;
margin-top: 4px;
```

### Timestamps

```css
font-family: Franklin Gothic, sans-serif;
font-size: 0.875rem;
color: #696969;
```

#### Formato típico

- Published: Jan. 15, 2024
- Updated: Jan. 16, 2024, 3:45 p.m. ET

---

## 12. ANIMACIONES Y TRANSICIONES

### Transiciones estándar

```css
transition: color 0.15s ease,
            background-color 0.2s ease,
            border-color 0.15s ease;
```

### Elementos con animación

- **Enlaces:** Color change en hover (0.15s)
- **Botones:** Background en hover (0.2s)
- **Imágenes:** Fade in al cargar
- **Sticky elements:** Smooth scroll behavior

### Preferencias de movimiento

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 13. ELEMENTOS ESPECÍFICOS NYT

### Header sticky

```css
position: sticky;
top: 0;
background-color: #FFFFFF;
border-bottom: 1px solid #E2E2E2;
z-index: 1000;
padding: 12px 20px;
```

### Masthead (Logo NYT)

- Fuente: Engravers' Old English BT (blackletter)
- Color: `#000000`
- Centrado en header móvil, izquierda en desktop

### Progress bar (artículos largos)

```css
position: fixed;
top: 0;
left: 0;
height: 3px;
background-color: #326891;
z-index: 9999;
```

### Related articles

```css
background-color: #F7F7F7;
padding: 24px;
margin: 40px 0;
border-left: 3px solid #666666;
```

#### Título de sección

```css
font-size: 0.875rem;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.5px;
color: #666666;
margin-bottom: 16px;
```

### Newsletter signup

```css
background-color: #326891;
color: #FFFFFF;
padding: 32px;
margin: 40px 0;
text-align: center;
```

---

## 14. ACCESIBILIDAD

### Características implementadas

1. **Color contrast** cumple WCAG AAA:
   - Texto principal: `#121212` sobre `#FFFFFF` (ratio ~19:1)
   - Enlaces: `#326891` sobre `#FFFFFF` (ratio ~5.5:1)
2. **Focus states** claramente visibles
3. **Skip links** para navegación por teclado
4. **ARIA labels** en elementos interactivos
5. **Alt text** obligatorio en imágenes
6. **Semantic HTML** (article, section, aside, nav)

### Focus visible

```css
*:focus-visible {
  outline: 2px solid #326891;
  outline-offset: 2px;
}
```

---

## 15. CÓDIGO Y ELEMENTOS TÉCNICOS

### Bloques de código (cuando se usan)

```css
background-color: #F7F7F7;
border: 1px solid #DFDFDF;
border-radius: 4px;
padding: 16px;
font-family: 'Courier New', monospace;
font-size: 0.875rem;
line-height: 1.5;
overflow-x: auto;
```

### Inline code

```css
background-color: #F7F7F7;
padding: 2px 6px;
border-radius: 3px;
font-family: 'Courier New', monospace;
font-size: 0.9em;
color: #D0021B;
```

---

## RESUMEN DE VALORES CLAVE PARA IMPLEMENTAR

### Espaciado estándar NYT

- **12px** - Espacios pequeños (inline, list items)
- **20px** - Espacios medianos (padding base, márgenes)
- **32px** - Espacios grandes (entre secciones)
- **40px** - Espacios extra grandes (separación mayor)

### Border-radius

- **2px** - Botones, tags (mínimo)
- **4px** - Bloques de código, cajas (sutil)

### Font-sizes principales

- **2.625rem (42px)** - H1 (títulos principales)
- **2rem (32px)** - H2
- **1.5rem (24px)** - H3
- **1.25rem (20px)** - H4
- **1.125rem (18px)** - Cuerpo de texto
- **0.9375rem (15px)** - Byline, subtexto
- **0.875rem (14px)** - Captions, metadata
- **0.75rem (12px)** - Labels, tags

### Colores esenciales

```css
--nyt-black: #000000;
--nyt-text: #121212;
--nyt-text-secondary: #363636;
--nyt-gray: #666666;
--nyt-blue: #326891;
--nyt-blue-dark: #244966;
--nyt-border: #DFDFDF;
--nyt-border-light: #E2E2E2;
--nyt-bg-alt: #F7F7F7;
--nyt-breaking: #D0021B;
--nyt-opinion: #F4D555;
--nyt-highlight: #FFF1C2;
```

---

## 16. PRINCIPIOS DE DISEÑO NYT

### Jerarquía clara

1. Título grande y bold
2. Byline prominente con autor
3. Fecha claramente visible
4. Lead paragraph más grande (drop cap opcional)
5. Contenido con ritmo visual consistente

### Espaciado generoso

- Márgenes amplios para facilitar lectura
- Espaciado vertical consistente
- White space como elemento de diseño

### Tipografía serif dominante

- Georgia para cuerpo (legibilidad excepcional)
- Cheltenham para títulos (carácter editorial)
- Sans-serif solo para UI y metadatos

### Minimalismo elegante

- Paleta de colores restringida
- Pocas decoraciones
- Enfoque en el contenido
- Diseño atemporal

---

**Fin del análisis**

## DIFERENCIAS CLAVE: NYT vs NATURE

| Aspecto | NYT | Nature |
|:--------|:----|:-------|
| **Tipografía cuerpo** | Georgia (serif) | Harding/Palatino (serif) |
| **Tamaño cuerpo** | 18px | 18px |
| **Line height** | 1.625 | 1.76 |
| **Color texto** | `#121212` | `#222222` |
| **Enlaces** | `#326891` (azul) | `#006699` (azul) |
| **Callouts** | Borde izquierdo | Borde inferior |
| **Estilo** | Editorial clásico | Científico profesional |
| **Espaciado** | Moderado | Generoso |
