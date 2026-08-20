# Glosario HTML5 — Guía rápida de estructura y elementos

> Referencia de consulta para recordar **qué hace cada elemento HTML**, **dónde se utiliza** y **cómo se ordena el código**.
>
> El término **HTML5** se usa aquí en el sentido habitual de HTML moderno. Actualmente HTML evoluciona como un estándar vivo (*HTML Living Standard*).

---

## Índice

1. [Estructura mínima de un documento HTML](#1-estructura-mínima-de-un-documento-html)
2. [Cómo se ordena normalmente una página](#2-cómo-se-ordena-normalmente-una-página)
3. [Conceptos básicos](#3-conceptos-básicos)
4. [Raíz y cabecera del documento](#4-raíz-y-cabecera-del-documento)
5. [Estructura semántica del body](#5-estructura-semántica-del-body)
6. [Agrupación y contenido de texto](#6-agrupación-y-contenido-de-texto)
7. [Texto en línea y formato semántico](#7-texto-en-línea-y-formato-semántico)
8. [Enlaces](#8-enlaces)
9. [Imágenes y multimedia](#9-imágenes-y-multimedia)
10. [Contenido incrustado](#10-contenido-incrustado)
11. [Tablas](#11-tablas)
12. [Formularios](#12-formularios)
13. [Tipos de input](#13-tipos-de-input)
14. [Elementos interactivos](#14-elementos-interactivos)
15. [JavaScript y contenido dinámico](#15-javascript-y-contenido-dinámico)
16. [Web Components y elementos avanzados](#16-web-components-y-elementos-avanzados)
17. [Atributos globales](#17-atributos-globales)
18. [Atributos frecuentes por contexto](#18-atributos-frecuentes-por-contexto)
19. [Elementos vacíos](#19-elementos-vacíos)
20. [Reglas rápidas de anidación](#20-reglas-rápidas-de-anidación)
21. [Elementos obsoletos](#21-elementos-obsoletos)
22. [Plantillas rápidas](#22-plantillas-rápidas)
23. [Fuentes de referencia](#23-fuentes-de-referencia)

---

# 1. Estructura mínima de un documento HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Título de la página</title>

    <link rel="stylesheet" href="css/estilos.css">
</head>

<body>

    <header>
        <!-- Encabezado visible -->
    </header>

    <nav>
        <!-- Navegación -->
    </nav>

    <main>
        <!-- Contenido principal -->
    </main>

    <footer>
        <!-- Pie de página -->
    </footer>

    <script src="js/funciones.js"></script>
</body>
</html>
```

## Orden principal

```text
<!DOCTYPE html>
└── <html>
    ├── <head>
    │   ├── <meta>
    │   ├── <title>
    │   ├── <link>
    │   └── otros metadatos/recursos
    │
    └── <body>
        ├── <header>
        ├── <nav>
        ├── <main>
        │   ├── <section>
        │   ├── <article>
        │   └── <aside>
        ├── <footer>
        └── <script>
```

> `<header>`, `<nav>`, `<main>` y `<footer>` no tienen que aparecer obligatoriamente en ese orden, pero esta estructura es común y fácil de mantener.

---

# 2. Cómo se ordena normalmente una página

## Dentro de `<head>`

Orden recomendado para proyectos normales:

```html
<head>
    <!-- 1. Codificación -->
    <meta charset="UTF-8">

    <!-- 2. Configuración responsive -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- 3. Metadatos -->
    <meta name="description" content="Descripción de la página">

    <!-- 4. Título -->
    <title>Mi página</title>

    <!-- 5. CSS / recursos -->
    <link rel="stylesheet" href="css/estilos.css">

    <!-- 6. Scripts que deban cargarse en el head -->
    <script src="js/app.js" defer></script>
</head>
```

## Dentro de `<body>`

Una estructura semántica frecuente:

```html
<body>
    <header>
        ...
    </header>

    <nav>
        ...
    </nav>

    <main>
        <section>
            <article>
                ...
            </article>
        </section>

        <aside>
            ...
        </aside>
    </main>

    <footer>
        ...
    </footer>
</body>
```

---

# 3. Conceptos básicos

| Concepto | Definición breve |
|---|---|
| HTML | Lenguaje de marcado que define la estructura y significado del contenido de una página web. |
| Elemento | Unidad de HTML formada normalmente por etiqueta de apertura, contenido y cierre. |
| Etiqueta | Marcador como `<p>` o `</p>` que inicia o termina un elemento. |
| Atributo | Información adicional incluida en la etiqueta de apertura. |
| Contenido | Texto u otros elementos contenidos dentro de un elemento. |
| Elemento padre | Elemento que contiene a otro. |
| Elemento hijo | Elemento contenido directamente dentro de otro. |
| Elemento hermano | Elemento que comparte el mismo padre con otro. |
| Anidación | Colocar elementos dentro de otros respetando su jerarquía. |
| DOM | Representación del documento HTML como árbol de objetos que JavaScript puede consultar y modificar. |
| Semántica | Uso de elementos según el significado del contenido, no solo por su apariencia. |

## Ejemplo de elemento

```html
<a href="productos.html" class="enlace">Productos</a>
```

- `<a>` → elemento.
- `href` → atributo.
- `class` → atributo.
- `Productos` → contenido.
- `</a>` → cierre.

## Comentarios HTML

```html
<!-- Este texto no se muestra en la página -->
```

Sirven para documentar el código.

---

# 4. Raíz y cabecera del documento

Estos elementos forman la base del archivo HTML.

| Elemento | Qué hace | Dónde va |
|---|---|---|
| `<!DOCTYPE html>` | Indica al navegador que el documento utiliza HTML moderno. | Primera línea del archivo. |
| `<html>` | Elemento raíz que contiene todo el documento. | Después del `DOCTYPE`. |
| `<head>` | Contiene metadatos y recursos que describen/configuran la página. | Primer hijo principal de `<html>`. |
| `<body>` | Contiene el contenido visible y funcional de la página. | Después de `<head>`. |
| `<title>` | Define el título de la pestaña del navegador. | Dentro de `<head>`. |
| `<meta>` | Define metadatos como codificación, viewport o descripción. | Normalmente dentro de `<head>`. |
| `<link>` | Vincula recursos externos, especialmente CSS e iconos. | Normalmente dentro de `<head>`. |
| `<style>` | Contiene CSS escrito directamente en el documento. | Generalmente dentro de `<head>`. |
| `<base>` | Define una URL base para las URLs relativas del documento. | Dentro de `<head>`. Solo uno por documento. |

### Ejemplo

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Tienda</title>

    <link rel="stylesheet" href="css/bootstrap.min.css">
    <link rel="stylesheet" href="css/estilos.css">
</head>
```

---

# 5. Estructura semántica del body

Sirven para dividir el contenido según su función.

| Elemento | Qué hace | Uso habitual |
|---|---|---|
| `<header>` | Contenido introductorio de una página o sección. | Logo, título, buscador, introducción. |
| `<nav>` | Agrupa enlaces de navegación importantes. | Menú principal, índice, navegación interna. |
| `<main>` | Contiene el contenido principal de la página. | Normalmente uno por documento visible. |
| `<section>` | Agrupa contenido relacionado bajo un tema. | Secciones temáticas, normalmente con encabezado. |
| `<article>` | Contenido independiente y reutilizable. | Noticias, posts, productos, comentarios. |
| `<aside>` | Contenido secundario relacionado indirectamente. | Barra lateral, recomendaciones, información adicional. |
| `<footer>` | Pie de una página o sección. | Copyright, autor, enlaces secundarios. |
| `<address>` | Información de contacto relacionada con una página o artículo. | Autor, empresa, contacto. |
| `<search>` | Zona dedicada a búsqueda o filtrado. | Formularios de búsqueda y filtros. |
| `<h1>` | Encabezado de mayor nivel. | Título principal o encabezado de nivel 1. |
| `<h2>` | Encabezado de segundo nivel. | Subsección de un `<h1>`. |
| `<h3>` | Encabezado de tercer nivel. | Subsección de un `<h2>`. |
| `<h4>` | Encabezado de cuarto nivel. | Nivel jerárquico inferior. |
| `<h5>` | Encabezado de quinto nivel. | Nivel jerárquico inferior. |
| `<h6>` | Encabezado de sexto nivel. | Nivel más bajo disponible. |
| `<hgroup>` | Agrupa un título con subtítulo o contenido secundario de encabezado. | Título + subtítulo o lema. |

## Jerarquía de encabezados

```html
<h1>Tienda</h1>

<section>
    <h2>Productos</h2>

    <article>
        <h3>Notebook</h3>
    </article>
</section>
```

Evita elegir `<h1>`–`<h6>` por tamaño visual. La apariencia se controla con CSS.

---

# 6. Agrupación y contenido de texto

| Elemento | Qué hace | Dónde/para qué se usa |
|---|---|---|
| `<p>` | Define un párrafo. | Dentro de `<body>` y sus secciones. |
| `<div>` | Contenedor genérico sin significado semántico propio. | Agrupar contenido para CSS, JS o layout. |
| `<ul>` | Lista sin orden. | Contiene `<li>`. |
| `<ol>` | Lista ordenada. | Contiene `<li>`. |
| `<li>` | Elemento de una lista. | Dentro de `<ul>`, `<ol>` o `<menu>`. |
| `<menu>` | Lista semántica de elementos/comandos. | Similar en comportamiento a `<ul>`. |
| `<dl>` | Lista de términos y descripciones. | Contiene `<dt>` y `<dd>`. |
| `<dt>` | Término de una lista descriptiva. | Dentro de `<dl>`. |
| `<dd>` | Descripción del término anterior. | Dentro de `<dl>`. |
| `<blockquote>` | Cita extensa en bloque. | Para citas de varios fragmentos o párrafos. |
| `<pre>` | Conserva espacios y saltos de línea. | Código, texto preformateado, diagramas simples. |
| `<figure>` | Contenido autónomo relacionado con el texto. | Imagen, gráfico, código, diagrama. |
| `<figcaption>` | Leyenda de un `<figure>`. | Dentro de `<figure>`. |
| `<hr>` | Separación temática entre contenidos. | Entre bloques o cambios de tema. |

## Listas

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

```html
<ol>
    <li>Crear archivo</li>
    <li>Escribir HTML</li>
    <li>Abrir en navegador</li>
</ol>
```

## Lista descriptiva

```html
<dl>
    <dt>HTML</dt>
    <dd>Estructura del contenido.</dd>

    <dt>CSS</dt>
    <dd>Presentación visual.</dd>
</dl>
```

---

# 7. Texto en línea y formato semántico

Estos elementos suelen utilizarse dentro de párrafos, títulos, listas u otros textos.

| Elemento | Qué hace |
|---|---|
| `<span>` | Contenedor genérico en línea para aplicar CSS o manipulación con JS. |
| `<strong>` | Indica importancia fuerte. |
| `<em>` | Indica énfasis en una parte del texto. |
| `<b>` | Llama visualmente la atención sin agregar importancia semántica. |
| `<i>` | Distingue texto por voz, término técnico, idioma, taxonomía u otro motivo. |
| `<u>` | Marca texto con una anotación no textual; suele verse subrayado. |
| `<small>` | Información secundaria o letra pequeña, como avisos legales. |
| `<mark>` | Resalta texto relevante en un contexto. |
| `<s>` | Texto que ya no es correcto o relevante. |
| `<abbr>` | Abreviatura o acrónimo. |
| `<dfn>` | Marca un término que está siendo definido. |
| `<cite>` | Marca el título de una obra citada. |
| `<q>` | Cita breve dentro de una línea de texto. |
| `<code>` | Fragmento corto de código. |
| `<kbd>` | Entrada que debe realizar el usuario, normalmente con teclado. |
| `<samp>` | Salida o resultado producido por un programa. |
| `<var>` | Variable matemática o de programación. |
| `<data>` | Vincula texto visible con un valor legible por máquina. |
| `<time>` | Representa una fecha u hora. |
| `<sub>` | Texto en subíndice. |
| `<sup>` | Texto en superíndice. |
| `<br>` | Fuerza un salto de línea. |
| `<wbr>` | Indica un punto donde el navegador puede cortar una palabra o línea. |
| `<bdi>` | Aísla la dirección de escritura de un fragmento. |
| `<bdo>` | Fuerza una dirección específica de escritura. |
| `<ruby>` | Contenedor para anotaciones tipográficas, comunes en idiomas asiáticos. |
| `<rt>` | Texto de la anotación de `<ruby>`. |
| `<rp>` | Texto alternativo para navegadores sin soporte de anotaciones ruby. |
| `<ins>` | Contenido agregado a una versión del documento. |
| `<del>` | Contenido eliminado de una versión del documento. |

### Ejemplos

```html
<p>Este texto es <strong>importante</strong>.</p>

<p>Presiona <kbd>Ctrl</kbd> + <kbd>S</kbd>.</p>

<p>La función <code>console.log()</code> muestra información en consola.</p>

<p>Oferta válida hasta el <time datetime="2026-08-31">31 de agosto</time>.</p>
```

---

# 8. Enlaces

| Elemento | Qué hace |
|---|---|
| `<a>` | Crea un enlace o hipervínculo mediante `href`. |

### Enlace a otra página

```html
<a href="productos.html">Productos</a>
```

### Enlace externo

```html
<a href="https://example.com" target="_blank" rel="noopener">
    Visitar sitio
</a>
```

### Enlace a una sección

```html
<a href="#contacto">Ir a contacto</a>

<section id="contacto">
    ...
</section>
```

### Correo

```html
<a href="mailto:correo@example.com">Enviar correo</a>
```

---

# 9. Imágenes y multimedia

| Elemento | Qué hace | Relación |
|---|---|---|
| `<img>` | Inserta una imagen. | Usa normalmente `src` y `alt`. |
| `<picture>` | Permite ofrecer distintas versiones de una imagen. | Contiene `<source>` y `<img>`. |
| `<source>` | Define una fuente alternativa para imagen, audio o video. | Dentro de `<picture>`, `<audio>` o `<video>`. |
| `<audio>` | Inserta un reproductor de audio. | Puede contener `<source>` y `<track>`. |
| `<video>` | Inserta un reproductor de video. | Puede contener `<source>` y `<track>`. |
| `<track>` | Añade subtítulos, captions u otros textos sincronizados. | Dentro de `<audio>` o `<video>`. |
| `<map>` | Define un mapa de imagen con zonas clicables. | Se asocia a `<img>`. |
| `<area>` | Define una zona clicable de un `<map>`. | Dentro de `<map>`. |

## Imagen

```html
<img src="img/producto.jpg" alt="Notebook negro sobre un escritorio">
```

## Figure

```html
<figure>
    <img src="img/grafico.png" alt="Ventas mensuales">
    <figcaption>Ventas del primer semestre.</figcaption>
</figure>
```

## Video

```html
<video controls>
    <source src="video/demo.mp4" type="video/mp4">
    Tu navegador no puede reproducir este video.
</video>
```

---

# 10. Contenido incrustado

| Elemento | Qué hace |
|---|---|
| `<iframe>` | Inserta otra página o documento dentro de la página actual. |
| `<embed>` | Inserta contenido externo compatible con el navegador. |
| `<object>` | Inserta un recurso externo que puede tratarse como documento, imagen u objeto incrustado. |

### Ejemplo

```html
<iframe
    src="pagina.html"
    title="Contenido incrustado">
</iframe>
```

---

# 11. Tablas

Una tabla representa **datos tabulares**, no debería utilizarse para construir el diseño general de una página.

## Orden habitual

```text
<table>
├── <caption>
├── <colgroup>
│   └── <col>
├── <thead>
│   └── <tr>
│       └── <th>
├── <tbody>
│   └── <tr>
│       └── <td>
└── <tfoot>
    └── <tr>
        └── <td>
```

| Elemento | Qué hace |
|---|---|
| `<table>` | Contenedor principal de una tabla. |
| `<caption>` | Título o descripción breve de la tabla. |
| `<thead>` | Agrupa las filas de encabezado. |
| `<tbody>` | Agrupa las filas principales de datos. |
| `<tfoot>` | Agrupa filas de resumen o pie. |
| `<tr>` | Define una fila. |
| `<th>` | Define una celda de encabezado. |
| `<td>` | Define una celda de datos. |
| `<colgroup>` | Agrupa columnas para aplicar propiedades comunes. |
| `<col>` | Representa una o más columnas dentro de `<colgroup>`. |

## Ejemplo

```html
<table>
    <caption>Productos</caption>

    <thead>
        <tr>
            <th scope="col">Producto</th>
            <th scope="col">Precio</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Teclado</td>
            <td>$19.990</td>
        </tr>

        <tr>
            <td>Mouse</td>
            <td>$9.990</td>
        </tr>
    </tbody>
</table>
```

---

# 12. Formularios

## Estructura básica

```html
<form action="/procesar" method="post">

    <div>
        <label for="nombre">Nombre:</label>
        <input
            type="text"
            id="nombre"
            name="nombre"
            required>
    </div>

    <button type="submit">Enviar</button>

</form>
```

| Elemento | Qué hace |
|---|---|
| `<form>` | Agrupa controles para ingresar y enviar información. |
| `<label>` | Describe un control del formulario. |
| `<input>` | Control de entrada cuyo funcionamiento depende de `type`. |
| `<textarea>` | Campo de texto de varias líneas. |
| `<button>` | Botón que ejecuta una acción. |
| `<select>` | Lista desplegable de opciones. |
| `<option>` | Opción dentro de `<select>` o `<datalist>`. |
| `<optgroup>` | Agrupa opciones relacionadas dentro de un `<select>`. |
| `<datalist>` | Lista de sugerencias asociada normalmente a un `<input>`. |
| `<fieldset>` | Agrupa controles relacionados. |
| `<legend>` | Título de un `<fieldset>`. |
| `<output>` | Muestra el resultado de una operación o cálculo. |
| `<progress>` | Indica el progreso de una tarea. |
| `<meter>` | Representa un valor dentro de un rango conocido. |

## Relación correcta entre label e input

```html
<label for="correo">Correo:</label>
<input type="email" id="correo" name="correo">
```

`for="correo"` debe coincidir con `id="correo"`.

## Fieldset

```html
<fieldset>
    <legend>Datos personales</legend>

    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre">

    <label for="edad">Edad:</label>
    <input type="number" id="edad" name="edad">
</fieldset>
```

---

# 13. Tipos de input

`<input>` cambia de comportamiento mediante el atributo `type`.

| Tipo | Uso |
|---|---|
| `text` | Texto de una línea. |
| `password` | Contraseña con caracteres ocultos visualmente. |
| `email` | Dirección de correo electrónico. |
| `number` | Número. |
| `tel` | Número telefónico. |
| `url` | Dirección URL. |
| `search` | Campo de búsqueda. |
| `date` | Fecha. |
| `datetime-local` | Fecha y hora local. |
| `month` | Mes y año. |
| `week` | Semana y año. |
| `time` | Hora. |
| `color` | Selector de color. |
| `range` | Control deslizante dentro de un rango. |
| `checkbox` | Casilla independiente de selección. |
| `radio` | Opción exclusiva dentro de un grupo. |
| `file` | Selección de archivo. |
| `hidden` | Dato oculto visualmente enviado con el formulario. |
| `button` | Botón genérico sin acción predeterminada. |
| `submit` | Envía el formulario. |
| `reset` | Restablece los valores del formulario. |
| `image` | Botón gráfico de envío. |

## Radio buttons

Los elementos del mismo grupo comparten el mismo `name`.

```html
<input type="radio" id="retiro" name="entrega" value="retiro">
<label for="retiro">Retiro</label>

<input type="radio" id="despacho" name="entrega" value="despacho">
<label for="despacho">Despacho</label>
```

## Checkbox

```html
<input type="checkbox" id="terminos" name="terminos">
<label for="terminos">Acepto los términos</label>
```

---

# 14. Elementos interactivos

| Elemento | Qué hace |
|---|---|
| `<details>` | Crea un bloque que puede abrirse y cerrarse. |
| `<summary>` | Título clicable de un `<details>`. |
| `<dialog>` | Representa un cuadro de diálogo o ventana interactiva. |

## Details

```html
<details>
    <summary>Ver información</summary>
    <p>Contenido adicional.</p>
</details>
```

## Dialog

```html
<dialog id="ventana">
    <p>Contenido del diálogo.</p>
    <button>Cerrar</button>
</dialog>
```

Normalmente su apertura/cierre se controla con JavaScript.

---

# 15. JavaScript y contenido dinámico

| Elemento | Qué hace |
|---|---|
| `<script>` | Inserta o enlaza código JavaScript u otros datos interpretables. |
| `<noscript>` | Contenido alternativo cuando JavaScript no está disponible. |
| `<canvas>` | Superficie gráfica controlada normalmente mediante JavaScript. |

## Script externo

```html
<script src="js/funciones.js"></script>
```

Colocarlo al final de `<body>` permite que el HTML anterior ya exista cuando el script se ejecuta.

## Script con defer

```html
<head>
    <script src="js/funciones.js" defer></script>
</head>
```

`defer` permite descargar el script sin bloquear el análisis del HTML y ejecutarlo cuando el documento ya fue procesado.

## Canvas

```html
<canvas id="grafico" width="600" height="400"></canvas>
```

---

# 16. Web Components y elementos avanzados

| Elemento | Qué hace |
|---|---|
| `<template>` | Guarda HTML que no se renderiza inmediatamente y puede clonarse con JavaScript. |
| `<slot>` | Punto de inserción de contenido dentro de un Web Component. |
| `<svg>` | Inserta gráficos vectoriales SVG directamente dentro de HTML. |
| `<math>` | Inserta contenido MathML para fórmulas matemáticas. |

## Elementos nuevos o experimentales

Estos elementos pueden tener soporte limitado o evolucionar con el estándar.

| Elemento | Función |
|---|---|
| `<selectedcontent>` | Representa el contenido seleccionado en ciertos controles `<select>` personalizables. |
| `<geolocation>` | Control experimental relacionado con compartir geolocalización. |
| `<fencedframe>` | Contexto incrustado experimental con restricciones orientadas a privacidad. |

> Antes de usar elementos experimentales en una actividad, revisa compatibilidad y requisitos del navegador.

---

# 17. Atributos globales

Los atributos globales pueden utilizarse en muchos o todos los elementos HTML, aunque algunos solo producen efectos en determinados contextos.

| Atributo | Qué hace |
|---|---|
| `id` | Identificador único de un elemento dentro del documento. |
| `class` | Asigna una o más clases para CSS o JavaScript. |
| `style` | Agrega CSS directamente al elemento. |
| `title` | Información adicional asociada al elemento. |
| `lang` | Define el idioma del contenido. |
| `dir` | Define dirección del texto: `ltr`, `rtl` o `auto`. |
| `hidden` | Oculta semánticamente el elemento. |
| `tabindex` | Controla participación/orden en navegación por teclado. |
| `accesskey` | Define una tecla de acceso rápido. |
| `contenteditable` | Permite editar el contenido desde la interfaz. |
| `draggable` | Indica si el elemento puede arrastrarse. |
| `spellcheck` | Activa o desactiva corrección ortográfica cuando corresponda. |
| `translate` | Indica si el contenido debería traducirse. |
| `data-*` | Permite almacenar datos personalizados en el elemento. |
| `autofocus` | Solicita foco automático al cargar/mostrar el elemento. |
| `autocapitalize` | Sugiere comportamiento de mayúsculas en entrada de texto. |
| `autocorrect` | Controla corrección automática donde exista soporte. |
| `inputmode` | Sugiere el tipo de teclado virtual apropiado. |
| `enterkeyhint` | Sugiere la función visual de la tecla Enter en teclado virtual. |
| `inert` | Hace que un árbol de contenido no sea interactivo. |
| `popover` | Permite utilizar un elemento como contenido emergente. |
| `slot` | Asigna el elemento a un `<slot>` de un Web Component. |
| `part` | Expone una parte de un Web Component para estilizarla. |
| `exportparts` | Reexpone partes internas de un Web Component. |
| `is` | Identifica ciertos elementos personalizados. |
| `nonce` | Valor utilizado por políticas de seguridad de contenido. |
| `itemscope` | Declara un elemento como ítem de microdatos. |
| `itemtype` | Define el tipo del ítem de microdatos. |
| `itemprop` | Define una propiedad de microdatos. |
| `itemid` | Identificador global de un ítem de microdatos. |
| `itemref` | Relaciona propiedades de microdatos ubicadas fuera del elemento. |

> Algunos atributos globales recientes o experimentales pueden tener soporte parcial. En actividades académicas básicas normalmente utilizarás sobre todo `id`, `class`, `style`, `title`, `lang`, `hidden` y `data-*`.

---

# 18. Atributos frecuentes por contexto

## Enlaces

| Atributo | Uso |
|---|---|
| `href` | Destino del enlace. |
| `target` | Indica dónde abrir el destino. |
| `rel` | Define la relación entre el documento actual y el destino. |
| `download` | Sugiere descargar el recurso enlazado. |

## Imágenes

| Atributo | Uso |
|---|---|
| `src` | Ruta de la imagen. |
| `alt` | Texto alternativo de la imagen. |
| `width` | Ancho. |
| `height` | Alto. |
| `loading` | Controla carga diferida, por ejemplo `lazy`. |
| `srcset` | Define múltiples candidatos de imagen. |
| `sizes` | Ayuda a seleccionar una imagen de `srcset`. |

## Formularios

| Atributo | Uso |
|---|---|
| `name` | Nombre con el que se identifica/envía el dato. |
| `value` | Valor del control. |
| `placeholder` | Texto orientativo dentro del campo. |
| `required` | Hace obligatorio el campo. |
| `disabled` | Desactiva el control. |
| `readonly` | Impide editar manteniendo el valor disponible. |
| `checked` | Marca inicialmente checkbox o radio. |
| `selected` | Marca inicialmente una opción. |
| `min` | Valor mínimo. |
| `max` | Valor máximo. |
| `step` | Incremento permitido. |
| `minlength` | Longitud mínima de texto. |
| `maxlength` | Longitud máxima de texto. |
| `pattern` | Patrón de validación mediante expresión regular. |
| `multiple` | Permite seleccionar/ingresar varios valores cuando aplica. |
| `autocomplete` | Controla sugerencias/autocompletado del navegador. |
| `accept` | Limita tipos de archivo en `input type="file"`. |
| `list` | Vincula un `<input>` con un `<datalist>`. |
| `for` | Relaciona `<label>` con el `id` de un control. |

## `<form>`

| Atributo | Uso |
|---|---|
| `action` | URL que procesará los datos enviados. |
| `method` | Método HTTP, normalmente `get` o `post`. |
| `enctype` | Codificación usada al enviar el formulario. |
| `novalidate` | Desactiva la validación HTML automática del formulario. |

## Multimedia

| Atributo | Uso |
|---|---|
| `controls` | Muestra controles del reproductor. |
| `autoplay` | Intenta iniciar reproducción automáticamente. |
| `muted` | Inicia o mantiene el recurso silenciado. |
| `loop` | Repite el contenido. |
| `poster` | Imagen previa de un `<video>`. |
| `preload` | Sugiere cómo precargar audio/video. |

## Scripts

| Atributo | Uso |
|---|---|
| `src` | Ruta del archivo JavaScript. |
| `defer` | Ejecuta el script después de analizar el documento. |
| `async` | Ejecuta el script tan pronto termina de descargar. |
| `type="module"` | Trata el archivo como módulo JavaScript. |

---

# 19. Elementos vacíos

Los elementos vacíos no contienen contenido y no necesitan etiqueta de cierre.

Principales:

```text
<area>
<base>
<br>
<col>
<embed>
<hr>
<img>
<input>
<link>
<meta>
<source>
<track>
<wbr>
```

Ejemplo correcto:

```html
<img src="logo.png" alt="Logo">
```

No es necesario escribir:

```html
<img src="logo.png" alt="Logo" />
```

La barra final puede verse en algunos estilos de código, pero HTML moderno no la necesita.

---

# 20. Reglas rápidas de anidación

## 1. Cerrar en orden inverso

Correcto:

```html
<p>
    Texto <strong>importante</strong>.
</p>
```

Incorrecto:

```html
<p>
    <strong>Texto
</p>
    </strong>
```

---

## 2. `<head>` y `<body>` son hermanos

```html
<html>
    <head>
        ...
    </head>

    <body>
        ...
    </body>
</html>
```

No coloques `<body>` dentro de `<head>`.

---

## 3. Los elementos visuales de la página van en `<body>`

```html
<body>
    <h1>Título</h1>
    <p>Contenido</p>
</body>
```

---

## 4. `<li>` necesita una lista

Correcto:

```html
<ul>
    <li>Elemento</li>
</ul>
```

---

## 5. `<tr>` pertenece a una tabla

```html
<table>
    <tbody>
        <tr>
            <td>Dato</td>
        </tr>
    </tbody>
</table>
```

---

## 6. `<option>` pertenece a un control de opciones

```html
<select>
    <option value="1">Opción 1</option>
</select>
```

También puede utilizarse en `<datalist>`.

---

## 7. `<legend>` pertenece a `<fieldset>`

```html
<fieldset>
    <legend>Datos personales</legend>
</fieldset>
```

---

## 8. `<figcaption>` pertenece a `<figure>`

```html
<figure>
    <img src="grafico.png" alt="Gráfico">
    <figcaption>Resultados.</figcaption>
</figure>
```

---

## 9. `<summary>` pertenece a `<details>`

```html
<details>
    <summary>Más información</summary>
    <p>Contenido.</p>
</details>
```

---

## 10. Evita usar `<div>` para todo

Preferible:

```html
<header>...</header>
<nav>...</nav>
<main>...</main>
<section>...</section>
<footer>...</footer>
```

Usa `<div>` cuando no exista un elemento semántico adecuado o necesites un contenedor auxiliar para CSS/JS.

---

# 21. Elementos obsoletos

Estos elementos pueden aparecer en código antiguo, pero **no deberían utilizarse en proyectos nuevos**.

| Elemento obsoleto | Alternativa actual |
|---|---|
| `<acronym>` | `<abbr>` |
| `<big>` | CSS |
| `<center>` | CSS |
| `<dir>` | `<ul>` |
| `<font>` | CSS |
| `<frame>` | Evitar; usar estructura moderna o `<iframe>` según el caso. |
| `<frameset>` | Diseño moderno con HTML + CSS. |
| `<marquee>` | CSS/JavaScript cuando realmente se necesite animación. |
| `<nobr>` | CSS (`white-space`). |
| `<noembed>` | Contenido alternativo moderno. |
| `<noframes>` | Ya no es necesario. |
| `<param>` | Obsoleto. |
| `<plaintext>` | `<pre>` / escape de HTML. |
| `<strike>` | `<s>` o `<del>` según el significado. |
| `<tt>` | `<code>`, `<kbd>`, `<samp>` o CSS según el caso. |
| `<xmp>` | `<pre><code>...</code></pre>`. |
| `<content>` | `<slot>` en Web Components. |
| `<shadow>` | Shadow DOM moderno / `<slot>`. |
| `<menuitem>` | Controles modernos con botones y JavaScript. |
| `<rb>` | La sintaxis moderna de `<ruby>` normalmente no lo requiere. |
| `<rtc>` | Utilizar la sintaxis moderna de anotaciones ruby. |

---

# 22. Plantillas rápidas

## Página semántica simple

```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Mi sitio</title>

    <link rel="stylesheet" href="css/estilos.css">
</head>

<body>

    <header>
        <h1>Mi sitio</h1>
    </header>

    <nav>
        <ul>
            <li><a href="index.html">Inicio</a></li>
            <li><a href="productos.html">Productos</a></li>
            <li><a href="contacto.html">Contacto</a></li>
        </ul>
    </nav>

    <main>

        <section>
            <h2>Productos destacados</h2>

            <article>
                <h3>Producto 1</h3>
                <p>Descripción del producto.</p>
            </article>

        </section>

    </main>

    <footer>
        <p>&copy; 2026 Mi sitio</p>
    </footer>

    <script src="js/funciones.js"></script>
</body>

</html>
```

---

## Formulario simple

```html
<form action="/procesar" method="post">

    <div>
        <label for="nombre">Nombre:</label>
        <input
            type="text"
            id="nombre"
            name="nombre"
            required>
    </div>

    <div>
        <label for="correo">Correo:</label>
        <input
            type="email"
            id="correo"
            name="correo"
            required>
    </div>

    <div>
        <label for="mensaje">Mensaje:</label>
        <textarea
            id="mensaje"
            name="mensaje">
        </textarea>
    </div>

    <button type="submit">Enviar</button>

</form>
```

---

## Tabla simple

```html
<table>

    <thead>
        <tr>
            <th scope="col">Nombre</th>
            <th scope="col">Precio</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Producto A</td>
            <td>$10.000</td>
        </tr>

        <tr>
            <td>Producto B</td>
            <td>$15.000</td>
        </tr>
    </tbody>

</table>
```

---

# 23. Fuentes de referencia

Este glosario fue organizado como material de consulta y estudio a partir de referencias de HTML moderno.

- LenguajeHTML — HTML en español  
  https://lenguajehtml.com/html/

- MDN Web Docs — Referencia de elementos HTML  
  https://developer.mozilla.org/es/docs/Web/HTML/Reference/Elements

- MDN Web Docs — Referencia HTML  
  https://developer.mozilla.org/es/docs/Web/HTML/Reference

- WHATWG — HTML Living Standard  
  https://html.spec.whatwg.org/

---

# Recordatorio rápido

Cuando tengas dudas sobre **dónde colocar algo**, piensa primero en esta jerarquía:

```text
DOCUMENTO
│
├── HEAD
│   ├── configuración
│   ├── metadatos
│   ├── título
│   └── CSS / recursos
│
└── BODY
    │
    ├── HEADER
    ├── NAV
    │
    ├── MAIN
    │   │
    │   ├── SECTION
    │   │   └── ARTICLE
    │   │
    │   ├── ARTICLE
    │   └── ASIDE
    │
    ├── FOOTER
    │
    └── SCRIPT
```

Y dentro del contenido:

```text
BLOQUES
├── títulos
├── párrafos
├── listas
├── imágenes
├── tablas
└── formularios
```

La regla principal es:

> **HTML define qué es cada contenido y cómo se estructura. CSS define cómo se ve. JavaScript define cómo se comporta.**
