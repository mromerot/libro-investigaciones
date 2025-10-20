# PROMPT PARA CONVERTIR CAPÍTULOS DE WORD A QUARTO MARKDOWN

Usa este prompt cuando conviertas un nuevo capítulo desde Word.

---

## INSTRUCCIONES PARA CLAUDE

**Contexto:**
Estoy convirtiendo capítulos de un libro científico desde formato Word a Quarto Markdown. El libro sigue un formato específico establecido en el Capítulo 1 de referencia.

**Tu tarea:**
Convertir el documento Word adjunto a formato Quarto Markdown siguiendo EXACTAMENTE la estructura y formato del archivo `01-conversion-template.md`.

---

## PASOS A SEGUIR

### PASO 1: Análisis del contenido Word
1. Lee el documento Word completo
2. Identifica:
   - Título del capítulo y autor(es)
   - Resumen/Abstract
   - Estructura de secciones (Introducción, Métodos, Resultados, Discusión, Conclusiones)
   - Tablas y figuras
   - Referencias bibliográficas
   - Ecuaciones o fórmulas matemáticas
   - Cajas informativas o callouts

### PASO 2: Crear el YAML Header
Usa la plantilla exacta del archivo `01-conversion-template.md`:
- **title:** Extraer del documento
- **author:** Extraer del documento
- **date:** "2025" (por defecto)
- **title-block-banner:** Usar `bannerCN.png` donde N es el número del capítulo
- **keywords:** Extraer o inferir 5 palabras clave en inglés
- Mantener todos los demás campos exactamente como en la plantilla

### PASO 3: Convertir Resumen y Abstract
- Si hay resumen en español → bloque `#resumen`
- Si hay abstract en inglés → bloque `#abstract`
- Si solo hay uno, crear el otro mediante traducción
- Mantener formato de bloques con `:::`

### PASO 4: Convertir Secciones
- **Encabezados principales:** `# 1. INTRODUCCIÓN` (MAYÚSCULAS)
- **Subsecciones:** `## 1.1 Título` (Primera letra mayúscula)
- **Sub-subsecciones:** `### Título` (Primera letra mayúscula)
- Mantener numeración original del documento

### PASO 5: Convertir Tablas
Para cada tabla:
1. Convertir a formato Markdown con alineación centrada: `|:---------:|`
2. Agregar caption DEBAJO de la tabla: `: Descripción. {#tbl-tablaN}`
3. Actualizar referencias en el texto a `@tbl-tablaN`
4. **Importante:** Fuente será Arial 12px automáticamente (por CSS)

**Ejemplo:**
```markdown
| Nombre | Año |
|:------:|:---:|
| Item 1 | 2021|
| Item 2 | 2022|

: Descripción de la tabla. {#tbl-tabla1}
```

### PASO 6: Convertir Figuras
Para cada figura:
1. **Si es imagen externa:**
   ```markdown
   ![Descripción de la figura.](ruta/imagen.png){#fig-figuraN width="383"}
   ```
2. **Si es gráfico que requiere interactividad:** Convertir a código OJS/D3
3. Actualizar referencias en el texto a `@fig-figuraN`
4. Guardar nombres de archivos de imágenes para que el usuario los agregue después

### PASO 7: Convertir Ecuaciones
- **En línea:** `$\lambda=\frac{1}{79}$`
- **En bloque:**
  ```markdown
  $$
  p(x)=\frac{e^{-\lambda} \lambda^{x}}{x !}
  $$
  ```

### PASO 8: Identificar y Convertir Cajas Informativas
Busca cuadros, recuadros o texto destacado en el Word:

**Para cajas intermedias (Box 1, Box 2...):**
```markdown
::: {#box1 .callout-important style="background-color: #e3f0fbff; border-left: 4px solid #d4e8f9ff;" appearance="minimal" icon="false"}
<h2 style="font-size: 1rem; margin-top: 0; margin-bottom: 0;">Caja 1. Título</h2>
-   Punto 1
-   Punto 2
:::
```

**Para sección de Conclusiones, SIEMPRE crear estas 3 cajas:**

1. **Puntos Clave** (fondo amarillo):
```markdown
::: {#puntos-clave .callout-important style="background-color: #f8f0ddff; border-left: 4px solid #f7eed3ff;" appearance="minimal" icon="false"}
<h2 style="font-size: 1.5rem; margin-top: 0; margin-bottom: 0;">Puntos Clave</h2>
-   [Extraer puntos principales de las conclusiones]
:::
```

2. **Preguntas por Resolver** (fondo morado):
```markdown
::: {#preguntas .callout-important style="background-color: #f3eaf8ff; border-left: 4px solid #efe3f7ff;" appearance="minimal" icon="false"}
<h2 style="font-size: 1.5rem; margin-top: 0; margin-bottom: 0;">Preguntas por resolver</h2>
-   [Extraer preguntas o limitaciones del estudio]
:::
```

3. **Recomendaciones** (fondo rojo claro):
```markdown
::: {#recomendaciones .callout-important style="background-color: #f8dedcff; border-left: 4px solid #fad4d1ff;" appearance="minimal" icon="false"}
<h2 style="font-size: 1.5rem; margin-top: 0; margin-bottom: 0;">Recomendaciones para tomar decisiones</h2>
-   [Extraer recomendaciones prácticas o implicaciones]
:::
```

### PASO 9: Convertir Referencias Bibliográficas

1. **En el texto:**
   - Cambiar (Autor, 2020) → `[@autor2020]`
   - Cambiar (Autor et al., 2020) → `[@autor2020]`
   - Cambiar (Autor, 2020; Otro, 2021) → `[@autor2020; @otro2021]`

2. **Crear entradas .bib:**
   - Al final del documento, listar todas las referencias que necesitan ser agregadas a `references.bib`
   - Usar formato BibTeX
   - Seguir ejemplos de `referencias-ejemplo.bib`
   - Para cada referencia, crear un identificador único (ej: `autor2020`)

3. **Sección de bibliografía:**
   ```markdown
   # BIBLIOGRAFÍA

   ::: {#refs}
   :::
   ```

### PASO 10: Agregar Secciones Finales

Siempre incluir:
```markdown
# AGRADECIMIENTOS

[Texto de agradecimientos si existe en el Word, o placeholder]

# DECLARACIÓN DE AUTORÍA CREDIT

[Texto sobre contribuciones si existe, o placeholder estándar]
```

---

## FORMATO DE SALIDA

Entregar:

1. **Archivo capitulo-N.qmd completo** con todo el contenido convertido
2. **Lista de imágenes necesarias** con sus nombres de archivo
3. **Referencias BibTeX** para agregar a `references.bib`
4. **Notas sobre conversiones** si hubo elementos difíciles de convertir

---

## REGLAS CRÍTICAS

- ✅ NO inventar contenido
- ✅ NO omitir ninguna sección del Word
- ✅ RESPETAR el formato EXACTO de la plantilla
- ✅ USAR los mismos colores para las cajas de conclusiones
- ✅ MANTENER referencias cruzadas (@fig-, @tbl-)
- ✅ CONSERVAR todas las ecuaciones matemáticas
- ✅ INDICAR claramente lo que falta (imágenes, datos, etc.)

---

## EJEMPLO DE USO

**Prompt que usarás:**

```
Lee el archivo Word [nombre-archivo.docx] y conviértelo a Quarto Markdown siguiendo
las instrucciones del archivo `02-conversion-prompt.md` y usando la estructura de
`01-conversion-template.md`.

Este es el capítulo [N] del libro.

Genera:
1. El archivo .qmd completo
2. Lista de imágenes a preparar
3. Referencias BibTeX a agregar
```

---

## VERIFICACIÓN FINAL

Antes de entregar, verifica:
- [ ] YAML header completo y correcto
- [ ] Resumen y Abstract presentes
- [ ] Todas las secciones convertidas
- [ ] Tablas con formato centrado e IDs
- [ ] Figuras con IDs y referencias
- [ ] Cajas de conclusiones (3 tipos) incluidas
- [ ] Referencias bibliográficas convertidas
- [ ] Ecuaciones en formato LaTeX
- [ ] Secciones finales incluidas

---

## CONSULTA LA GUÍA DE ESTILOS

Para detalles específicos sobre colores, fuentes y espaciado, consulta el archivo `03-style-guide.md`.
