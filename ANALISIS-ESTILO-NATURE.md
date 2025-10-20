# Análisis de Estilo: Nature Climate Change

**Fecha:** 2025-01-19 **Artículo analizado:** https://www.nature.com/articles/s41558-025-02455-2 **Revista:** Nature Climate Change

------------------------------------------------------------------------

## 1. TIPOGRAFÍA

### Fuentes principales

| Elemento | Fuente | Tamaño | Peso | Espaciado |
|:--------------|:--------------|:--------------|:--------------|:--------------|
| **Título principal (H1)** | Harding, Palatino, serif | 2rem (32px) | 700 (Bold) | -0.0390625rem |
| **Subtítulo (H2)** | Harding, Palatino, serif | 1.5rem (24px) | 700 (Bold) | -0.0117156rem |
| **Subsección (H3)** | Harding, Palatino, serif | 1.25rem (20px) | 700 (Bold) | -0.0117156rem |
| **H4** | Sans-serif (system) | 1.125rem (18px) | 700 (Bold) | -0.0117156rem |
| **Cuerpo de texto** | Harding, Palatino, serif | 1.125rem (18px) | 400 (Regular) | Normal |
| **Metadatos** | System sans-serif | 0.875rem (14px) | 400 (Regular) | Normal |
| **Captions/Leyendas** | System sans-serif | 1rem (16px) | 400 (Regular) | Normal |

### Familias de fuentes

``` css
/* Títulos y cuerpo principal */
font-family: Harding, Palatino, serif;

/* Interfaz y metadatos */
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
             "Oxygen-Sans", Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
```

### Características tipográficas

-   **Line-height cuerpo:** 1.76 (espaciado generoso)
-   **Line-height títulos:** 1.2 - 1.4
-   **Antialiasing:** `-webkit-font-smoothing: antialiased` para títulos
-   **Letter-spacing:** Negativo en títulos para ajuste óptico

------------------------------------------------------------------------

## 2. PALETA DE COLORES

### Colores principales

| Uso                  | Hex Code  | RGB         | Descripción    |
|:---------------------|:----------|:------------|:---------------|
| **Fondo página**     | `#FFFFFF` | 255,255,255 | Blanco puro    |
| **Fondo body**       | `#EEEEEE` | 238,238,238 | Gris muy claro |
| **Texto principal**  | `#222222` | 34,34,34    | Negro suave    |
| **Enlaces**          | `#006699` | 0,102,153   | Azul Nature    |
| **Bordes/Líneas**    | `#D5D5D5` | 213,213,213 | Gris claro     |
| **Texto secundario** | `#6F6F6F` | 111,111,111 | Gris medio     |
| **Texto terciario**  | `#626262` | 98,98,98    | Gris oscuro    |

### Colores de acento

| Elemento               | Hex Code  | RGB         | Uso                      |
|:-----------------------|:----------|:------------|:-------------------------|
| **Botón primario**     | `#006699` | 0,102,153   | Botones principales      |
| **Hover botón**        | `#FFFFFF` | 255,255,255 | Estado hover (invertido) |
| **Cajas info (fondo)** | `#EBF1F5` | 235,241,245 | Cajas informativas       |
| **Cajas info (borde)** | `#EBF1F5` | 235,241,245 | Mismo color              |
| **Success**            | `#00B8B0` | 0,184,176   | Mensajes positivos       |
| **Error**              | `#C40606` | 196,6,6     | Mensajes de error        |
| **Warning**            | `#EDBC53` | 237,188,83  | Advertencias             |
| **Info**               | `#003F8D` | 0,63,141    | Información              |

### Colores de estructura

| Elemento             | Color     | Uso                               |
|:---------------------|:----------|:----------------------------------|
| **Separadores**      | `#CEDBE0` | Líneas divisorias entre metadatos |
| **Bordes secciones** | `#D5D5D5` | Líneas bajo títulos de sección    |
| **Fondo header**     | `#000000` | Header negro (borde inferior 5px) |
| **Fondo dropdown**   | `#000000` | Menús desplegables                |
| **Texto en negro**   | `#EEEEEE` | Texto sobre fondos oscuros        |

------------------------------------------------------------------------

## 3. ESTRUCTURA Y ORGANIZACIÓN

### Layout principal

```         
┌─────────────────────────────────────────┐
│          HEADER (Negro + Logo)          │
├─────────────────────────────────────────┤
│                                         │
│  ┌──────────────┐  ┌─────────────────┐ │
│  │              │  │                 │ │
│  │   ARTÍCULO   │  │    SIDEBAR      │ │
│  │    (60.2%)   │  │    (31.2%)      │ │
│  │              │  │                 │ │
│  │              │  │  - TOC          │ │
│  │              │  │  - Figuras      │ │
│  │              │  │  - Referencias  │ │
│  │              │  │                 │ │
│  └──────────────┘  └─────────────────┘ │
│     (8.6% gap)                          │
│                                         │
└─────────────────────────────────────────┘
```

### Proporciones

-   **Columna principal:** 60.2% del ancho
-   **Margen derecho:** 8.6%
-   **Sidebar:** 31.2%
-   **Responsive:** En \<1024px, columna al 100%

### Márgenes y espaciado

| Elemento                   | Valor                        |
|:---------------------------|:-----------------------------|
| **Contenedor máximo**      | 1280px                       |
| **Padding contenedor**     | 16px (móvil), 16px (desktop) |
| **Margen entre párrafos**  | 24px                         |
| **Margen entre secciones** | 40px                         |
| **Padding cajas info**     | 16px                         |
| **Espaciado en listas**    | 8px entre items              |

------------------------------------------------------------------------

## 4. CAJAS INFORMATIVAS Y CALLOUTS

### Estilos de cajas

#### Caja estándar (Editorial Summary)

``` css
background-color: #FFFFFF;
border: 1px solid #EEEEEE;
border-bottom: 4px solid [color-tipo];
border-radius: 2px;
padding: 16px;
font-size: 1rem;
line-height: 1.4;
```

#### Tipos de cajas por color de borde

| Tipo        | Color borde               | Uso                    |
|:------------|:--------------------------|:-----------------------|
| **Info**    | `#003F8D` (Azul oscuro)   | Información general    |
| **Success** | `#00B8B0` (Verde azulado) | Resultados positivos   |
| **Warning** | `#EDBC53` (Amarillo)      | Advertencias           |
| **Error**   | `#C40606` (Rojo)          | Errores o limitaciones |

### Cajas de autor/institución

``` css
background-color: #EBF1F5;
border: 4px solid #EBF1F5;
border-radius: 20px;
padding: 2px 11px 2px 8px;
font-size: 0.875rem;
color: #666666;
```

------------------------------------------------------------------------

## 5. ELEMENTOS VISUALES

### Botones

#### Botón primario

``` css
background-color: #006699;
border: 1px solid #006699;
border-radius: 2px;
color: #FFFFFF;
padding: 13px;
font-size: 0.875rem;
transition: background-color 0.2s ease-out;
```

#### Hover state

``` css
background-color: #FFFFFF;
color: #006699;
border: 1px solid #006699;
```

### Íconos

-   **Tamaño:** 1em (relativo al texto)
-   **Alineación:** `vertical-align: text-top`
-   **Color:** `fill: currentcolor` (heredan color del texto)

### Separadores

-   **Grosor:** 2px para títulos principales
-   **Grosor:** 1px para divisiones secundarias
-   **Color:** `#D5D5D5`
-   **Estilo:** Sólido, sin sombras

------------------------------------------------------------------------

## 6. FIGURAS Y TABLAS

### Figuras

#### Container

``` css
padding-bottom: 56.25%; /* Ratio 16:9 */
position: relative;
overflow: hidden;
```

#### Imagen

``` css
object-fit: cover;
width: 100%;
height: 100%;
position: absolute;
```

#### Caption

``` css
font-family: sans-serif;
font-size: 1rem;
line-height: 1.4;
color: #000000;
font-weight: normal;
```

### Tablas

``` css
border-collapse: collapse;
width: 100%;
margin: 1.5rem 0;
font-family: Arial, sans-serif;
font-size: 12px;
```

#### Celdas

``` css
border: 1px solid #D1D5DB;
padding: 0.75rem;
text-align: center;
```

#### Encabezados

``` css
background-color: #F9FAFB;
font-weight: 600;
```

------------------------------------------------------------------------

## 7. REFERENCIAS BIBLIOGRÁFICAS

### Formato de la lista

``` css
font-family: Harding, Palatino, serif;
font-size: 1rem;
line-height: 1.4;
```

### Estilo de entrada

-   **Numeración:** Decimal inside (1, 2, 3...)
-   **Layout:** Dos columnas:
    -   Izquierda: Número
    -   Derecha: Referencia completa
-   **Separación:** 1px border-top entre entradas
-   **Color:** Heredado del texto principal

### Enlaces en referencias

``` css
color: #006699;
text-decoration: underline;
word-break: break-word;
```

------------------------------------------------------------------------

## 8. RESPONSIVE DESIGN

### Breakpoints

| Tamaño | Ancho | Cambios |
|:---|:---|:---|
| **Móvil** | \< 540px | Layout de 1 columna, fuentes más pequeñas |
| **Tablet** | 540px - 767px | Ajustes intermedios |
| **Desktop pequeño** | 768px - 1023px | Mantiene 2 columnas |
| **Desktop grande** | ≥ 1024px | Layout completo con sidebar |

### Ajustes por tamaño

#### Móvil (\< 540px)

-   Sidebar desaparece
-   Columna principal: 100%
-   Fuentes reducidas 10-15%
-   Padding reducido

#### Tablet (540px - 1023px)

-   Sidebar visible pero flotante
-   Algunas secciones se colapsan
-   Navegación simplificada

------------------------------------------------------------------------

## 9. SECCIÓN DE ABSTRACT/RESUMEN

### Estilo visual

``` css
background-color: #EFF6FF; /* Azul muy claro */
padding: 2rem;
border-radius: 0.5rem;
border: 1px solid #DBEAFE;
margin: 2rem 0;
```

### Título de sección

``` css
color: #3B82F6; /* Azul brillante */
margin-top: 0;
border-bottom: 2px solid #BFDBFE;
padding-bottom: 0.5rem;
```

------------------------------------------------------------------------

## 10. METADATOS DEL ARTÍCULO

### Identificadores (DOI, fecha, tipo)

``` css
color: #222222;
font-size: 14px;
border-right: 2px solid #CEDBE0;
padding-right: 8px;
margin-right: 8px;
```

### Autores

``` css
font-size: 1rem;
display: inline;
list-style: none;
color: inherit;
```

#### Separadores

-   Entre autores: `,` (coma + espacio)
-   Último autor: `&` (ampersand con espacios)

### Fechas y métricas

``` css
font-size: 1rem;
line-height: 1.3;
color: #626262;
```

------------------------------------------------------------------------

## 11. ANIMACIONES Y TRANSICIONES

### Transiciones estándar

``` css
transition: background-color 0.2s ease-out,
            color 0.2s ease-out;
```

### Elementos con transición

-   **Botones:** Cambio de color en hover
-   **Enlaces:** Subrayado en hover
-   **Menús:** Aparición/desaparición
-   **Íconos:** Rotación SVG (0.2s duration)

### Preferencias de movimiento

``` css
@media (prefers-reduced-motion: reduce) {
  .c-skip-link {
    transition: top 0.3s ease-in-out 0s;
  }
}
```

------------------------------------------------------------------------

## 12. ELEMENTOS ESPECÍFICOS DE NATURE

### Barra de contexto (sticky)

``` css
box-shadow: 0 0 10px 0 rgba(51, 51, 51, 0.2);
position: sticky;
background: #FFFFFF;
```

### Reading companion (sidebar con tabs)

``` css
min-height: 389px;
max-width: 389px;
position: sticky;
```

#### Tabs

``` css
background-color: #EEEEEE;
border: 1px solid #D5D5D5;
padding: 8px 8px 8px 15px;
```

#### Tab activa

``` css
background-color: #FFFFFF;
border-bottom: 1px solid #FFFFFF;
font-weight: 700;
```

### Breadcrumbs

``` css
color: #000000;
font-size: 1rem;
list-style: none;
```

#### Enlaces

``` css
color: #666666;
```

#### Separador (chevron)

``` css
fill: #888888;
height: 10px;
width: 10px;
margin: 4px 4px 0;
```

------------------------------------------------------------------------

## 13. ACCESIBILIDAD

### Características implementadas

1.  **Skip links** para navegación por teclado
2.  **Color contrast** cumple WCAG AA:
    -   Texto: `#222222` sobre `#FFFFFF` (ratio \~15.8:1)
    -   Enlaces: `#006699` sobre `#FFFFFF` (ratio \~6.5:1)
3.  **Focus states** visibles en elementos interactivos
4.  **ARIA roles** en elementos semánticos
5.  **Responsive font sizing** mantiene legibilidad
6.  **Reduced motion** respeta preferencias del usuario

### Text-size-adjust

``` css
text-size-adjust: 100%;
```

Previene zoom automático en móviles.

------------------------------------------------------------------------

## 14. IMPRESIÓN

### Estilos para print

``` css
@media print {
  .c-header__menu,
  .c-skip-link,
  .c-ad {
    display: none;
  }
}
```

Oculta navegación, anuncios y elementos interactivos al imprimir.

------------------------------------------------------------------------

## 15. CÓDIGO Y ELEMENTOS TÉCNICOS

### Bloques de código

``` css
border: 1px solid #FFFFFF;
font-family: monospace;
margin: 0 0 24px;
padding: 20px;
background: [implícito: claro];
```

### Líneas de código

``` css
display: block;
overflow-wrap: break-word;
white-space: pre-wrap;
```

------------------------------------------------------------------------

## RESUMEN DE VALORES CLAVE PARA IMPLEMENTAR

### Espaciado estándar

-   **8px** - Espacios pequeños (gaps, padding interno)
-   **16px** - Espacios medianos (padding de cajas, márgenes)
-   **24px** - Espacios entre párrafos
-   **40px** - Espacios entre secciones

### Border-radius

-   **2px** - Botones, cajas estándar (sutil)
-   **20px** - Tags, badges (más redondeado)

### Font-sizes principales

-   **2rem (32px)** - H1
-   **1.5rem (24px)** - H2
-   **1.25rem (20px)** - H3
-   **1.125rem (18px)** - Cuerpo, H4
-   **1rem (16px)** - Elementos secundarios
-   **0.875rem (14px)** - Metadatos, elementos pequeños

### Colores esenciales

``` css
--color-primary: #006699;
--color-text: #222222;
--color-text-secondary: #6F6F6F;
--color-border: #D5D5D5;
--color-bg-page: #FFFFFF;
--color-bg-alt: #EEEEEE;
--color-bg-box: #EBF1F5;
--color-success: #00B8B0;
--color-error: #C40606;
--color-warning: #EDBC53;
--color-info: #003F8D;
```

------------------------------------------------------------------------

**Fin del análisis**

### Mis notas

``` {#Box .css .Box}
Caja 1 
--color-info: #003F8D;
```