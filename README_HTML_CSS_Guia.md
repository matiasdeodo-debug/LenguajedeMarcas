# Guía de HTML y CSS --- De básico a avanzado

> Manual de estudio y referencia para los ejercicios de Lenguajes de
> Marcas.\
> Incluye HTML básico, formato de texto, imágenes, enlaces, tablas,
> listas, formularios, estructura semántica y CSS desde selectores hasta
> posicionamiento y efectos.

------------------------------------------------------------------------

## Índice

1.  [Qué son HTML y CSS](#1-qué-son-html-y-css)
2.  [Estructura básica de HTML](#2-estructura-básica-de-html)
3.  [Etiquetas, atributos y
    comentarios](#3-etiquetas-atributos-y-comentarios)
4.  [Texto y formato](#4-texto-y-formato)
5.  [Enlaces](#5-enlaces)
6.  [Imágenes](#6-imágenes)
7.  [Listas](#7-listas)
8.  [Tablas](#8-tablas)
9.  [Formularios](#9-formularios)
10. [Estructura semántica de una
    página](#10-estructura-semántica-de-una-página)
11. [Cómo conectar CSS con HTML](#11-cómo-conectar-css-con-html)
12. [Sintaxis y selectores CSS](#12-sintaxis-y-selectores-css)
13. [Colores, fondos y tipografía](#13-colores-fondos-y-tipografía)
14. [El modelo de caja: margin, border y
    padding](#14-el-modelo-de-caja-margin-border-y-padding)
15. [Tamaños y visualización: width, height y
    display](#15-tamaños-y-visualización-width-height-y-display)
16. [Listas y formularios con CSS](#16-listas-y-formularios-con-css)
17. [Agrupación de elementos con div y
    span](#17-agrupación-de-elementos-con-div-y-span)
18. [Pseudoclases y pseudoelementos](#18-pseudoclases-y-pseudoelementos)
19. [Transformaciones y
    transiciones](#19-transformaciones-y-transiciones)
20. [Posicionamiento CSS](#20-posicionamiento-css)
21. [Overflow, z-index y scroll](#21-overflow-z-index-y-scroll)
22. [Ejemplos completos inspirados en las
    actividades](#22-ejemplos-completos-inspirados-en-las-actividades)
23. [Errores frecuentes](#23-errores-frecuentes)
24. [Checklist antes de entregar en
    GitHub](#24-checklist-antes-de-entregar-en-github)

------------------------------------------------------------------------

# 1. Qué son HTML y CSS

**HTML** (*HyperText Markup Language*) define la estructura y el
contenido de una página web: títulos, párrafos, imágenes, enlaces,
listas, tablas y formularios.

**CSS** (*Cascading Style Sheets*) define la presentación visual:
colores, tamaños, tipografías, márgenes, bordes, distribución,
posiciones y efectos.

Una forma sencilla de recordarlo:

-   HTML = qué elementos hay y qué significado tienen.
-   CSS = cómo se ven y dónde aparecen.

Ejemplo:

``` html
<p class="aviso">Bienvenido a mi página</p>
```

``` css
.aviso {
    color: blue;              /* Cambia el color del texto a azul */
    font-size: 20px;          /* Establece el tamaño del texto */
    background-color: #eee;   /* Añade un fondo gris claro */
}
```

El HTML crea el párrafo y CSS le da su aspecto.

# 2. Estructura básica de HTML

Todo documento HTML debe tener una estructura general.

``` html
<!DOCTYPE html> <!-- Indica al navegador que se utiliza HTML5 -->
<html lang="es"> <!-- Elemento raíz; lang indica que el contenido está en español -->
<head>
    <meta charset="UTF-8"> <!-- Permite mostrar tildes, ñ y otros caracteres -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Adapta el ancho de la página al dispositivo, especialmente móviles -->

    <title>Mi primera web</title> <!-- Texto que aparece en la pestaña del navegador -->
</head>
<body>
    <h1>Mi primera página</h1> <!-- Título principal visible -->
    <p>Estoy aprendiendo HTML.</p> <!-- Párrafo visible -->
</body>
</html>
```

**Qué hace cada parte:**

  -----------------------------------------------------------------------
  Elemento                            Función
  ----------------------------------- -----------------------------------
  `<!DOCTYPE html>`                   Declara que el documento utiliza
                                      HTML5.

  `<html lang="es">`                  Contiene todo el documento e indica
                                      el idioma.

  `<head>`                            Guarda información de configuración
                                      y metadatos.

  `<meta charset="UTF-8">`            Define la codificación de
                                      caracteres.

  `<meta name="viewport"...>`         Ayuda a que la web se adapte a
                                      pantallas pequeñas.

  `<title>`                           Define el título de la pestaña.

  `<body>`                            Contiene todo lo que se muestra en
                                      la página.
  -----------------------------------------------------------------------

# 3. Etiquetas, atributos y comentarios

Una etiqueta suele tener apertura y cierre:

``` html
<p>Este es el contenido del párrafo.</p>
```

-   `<p>` abre el párrafo.
-   `</p>` lo cierra.
-   El texto entre ambas etiquetas es el contenido.

Algunas etiquetas no necesitan cierre:

``` html
<img src="foto.jpg" alt="Descripción de la fotografía">
<br>
<hr>
```

-   `<img>` inserta una imagen.
-   `<br>` produce un salto de línea.
-   `<hr>` representa una separación temática, normalmente una línea
    horizontal.

## Atributos

Los atributos aportan información adicional a una etiqueta.

``` html
<a href="https://developer.mozilla.org/" target="_blank">
    Consultar documentación
</a>
```

-   `href` indica la dirección a la que lleva el enlace.
-   `target="_blank"` abre el enlace en otra pestaña.

Otros atributos habituales:

  -----------------------------------------------------------------------
  Atributo                            Para qué sirve
  ----------------------------------- -----------------------------------
  `id`                                Identifica de forma única un
                                      elemento dentro de la página.

  `class`                             Agrupa elementos para aplicarles
                                      estilos o seleccionarlos.

  `src`                               Indica la ruta de una imagen u otro
                                      recurso.

  `alt`                               Proporciona un texto alternativo
                                      para una imagen.

  `href`                              Indica el destino de un enlace.

  `title`                             Añade información complementaria,
                                      normalmente como ayuda emergente.

  `type`                              Define el tipo de un campo de
                                      formulario o de un botón.

  `name`                              Identifica el dato de un control al
                                      enviar un formulario.

  `value`                             Establece el valor inicial o
                                      enviado de un control.
  -----------------------------------------------------------------------

## Comentarios

Los comentarios sirven para dejar notas en el código. No aparecen en la
página.

``` html
<!-- Este comentario explica el siguiente bloque -->
<header>
    <h1>Mi sitio web</h1>
</header>
```

En CSS los comentarios se escriben así:

``` css
/* Este comentario explica una regla CSS */
h1 {
    color: darkgreen;
}
```

# 4. Texto y formato

HTML ofrece etiquetas para organizar y destacar el contenido textual.

## Títulos

``` html
<h1>Título principal</h1> <!-- Encabezado de mayor importancia -->
<h2>Título de una sección</h2> <!-- Encabezado de segundo nivel -->
<h3>Subapartado</h3> <!-- Encabezado de tercer nivel -->
<h4>Otro nivel</h4>
<h5>Otro nivel</h5>
<h6>Encabezado de menor nivel</h6>
```

Los encabezados expresan jerarquía. No conviene elegirlos solamente por
el tamaño visual: para cambiar el tamaño se utiliza CSS.

## Párrafos y saltos

``` html
<p>Este es un párrafo completo.</p>
<p>Este es otro párrafo independiente.</p>

<p>Primera línea.<br>Segunda línea dentro del mismo párrafo.</p>
```

-   `<p>` crea un párrafo.
-   `<br>` fuerza un salto de línea dentro del contenido.

## Formato semántico del texto

``` html
<p><strong>Importante:</strong> trae agua para la ruta.</p>
<!-- strong indica que el contenido tiene gran importancia -->

<p><em>Atención:</em> el horario puede cambiar.</p>
<!-- em añade énfasis al texto -->

<p>Este texto está en <b>negrita visual</b>.</p>
<!-- b llama la atención visualmente, sin aportar por sí sola importancia semántica -->

<p>Este texto está en <i>cursiva visual</i>.</p>
<!-- i marca una voz o estilo diferente, sin ser necesariamente énfasis -->

<p>Precio anterior: <del>30 €</del>. Precio actual: 20 €.</p>
<!-- del indica contenido eliminado -->

<p>La actividad empieza el <mark>sábado</mark>.</p>
<!-- mark resalta un fragmento -->

<p>Fórmula: H<sub>2</sub>O.</p>
<!-- sub coloca el texto como subíndice -->

<p>2<sup>3</sup> = 8.</p>
<!-- sup coloca el texto como superíndice -->

<blockquote>
    Una cita extensa puede colocarse en este bloque.
</blockquote>
<!-- blockquote representa una cita independiente -->
```

**Diferencia importante:** utiliza `strong` y `em` cuando el significado
sea importancia o énfasis. Utiliza CSS para decidir cómo se ven.

## Código y texto preformateado

``` html
<p>Para crear un párrafo se utiliza <code>&lt;p&gt;</code>.</p>
<!-- code representa un fragmento de código -->

<pre>
Línea uno
    Línea dos con espacios
Línea tres
</pre>
<!-- pre conserva espacios y saltos de línea -->
```

# 5. Enlaces

La etiqueta `<a>` crea enlaces.

## Enlace externo

``` html
<a href="https://www.wikipedia.org/">Visitar Wikipedia</a>
```

`href` contiene la dirección de destino.

## Abrir en otra pestaña

``` html
<a href="https://developer.mozilla.org/"
   target="_blank"
   rel="noopener noreferrer">
   Consultar MDN
</a>
```

-   `target="_blank"` abre otra pestaña.
-   `rel="noopener noreferrer"` añade protección y evita que la página
    de destino controle la pestaña de origen.

## Enlace a otra página del proyecto

``` html
<a href="contacto.html">Contacto</a>
```

La ruta apunta al archivo `contacto.html`.

## Enlace a una sección de la misma página

``` html
<nav>
    <a href="#inicio">Inicio</a>
    <a href="#contacto">Contacto</a>
</nav>

<section id="inicio">
    <h2>Inicio</h2>
</section>

<section id="contacto">
    <h2>Contacto</h2>
</section>
```

-   `href="#contacto"` busca el elemento cuyo `id` sea `contacto`.
-   El valor del `id` debe coincidir exactamente con el fragmento del
    enlace.
-   Un `id` debe ser único en el documento.

## Enlace para volver arriba

``` html
<header id="arriba">
    <h1>Mi página</h1>
</header>

<a href="#arriba">↑ Subir</a>
```

El enlace lleva al elemento que tiene `id="arriba"`.

# 6. Imágenes

La etiqueta `<img>` inserta una imagen. Es una etiqueta sin cierre.

``` html
<img src="imagenes/montana.jpg"
     alt="Montaña al amanecer"
     width="500">
```

  -----------------------------------------------------------------------
  Atributo                            Función
  ----------------------------------- -----------------------------------
  `src`                               Ruta del archivo de imagen.

  `alt`                               Descripción textual de la imagen;
                                      también ayuda a la accesibilidad.

  `width`                             Anchura de la imagen.

  `height`                            Altura de la imagen.
  -----------------------------------------------------------------------

Es recomendable que `alt` describa la imagen. Si una imagen es puramente
decorativa, puede utilizarse `alt=""`.

## Rutas de imágenes

Estructura posible:

``` text
mi-web/
├── index.html
├── estilos.css
└── imagenes/
    ├── logo.png
    └── paisaje.jpg
```

Desde `index.html`:

``` html
<img src="imagenes/logo.png" alt="Logotipo">
```

-   `imagenes/logo.png` es una ruta relativa a la carpeta actual.
-   `../` permite subir un nivel de carpetas.
-   También se puede utilizar una URL completa para una imagen alojada
    en Internet.

## Imagen con enlace

``` html
<a href="https://www.ejemplo.com/">
    <img src="imagenes/logo.png" alt="Ir a la página de ejemplo">
</a>
```

Al pulsar la imagen, se abre el enlace.

## Pie de foto semántico

``` html
<figure>
    <img src="imagenes/mar.jpg" alt="Vista del mar">
    <figcaption>Atardecer junto al mar.</figcaption>
</figure>
```

-   `<figure>` agrupa contenido ilustrativo.
-   `<figcaption>` añade su descripción o pie de foto.

## Controlar imágenes con CSS

``` css
img {
    max-width: 100%; /* Impide que la imagen sobrepase el ancho de su contenedor */
    height: auto;     /* Mantiene la proporción original */
    display: block;   /* Evita ciertos espacios de línea propios de imágenes inline */
}
```

# 7. Listas

## Lista desordenada

Se utiliza cuando el orden de los elementos no importa.

``` html
<ul>
    <li>Agua</li>
    <li>Comida</li>
    <li>Calzado cómodo</li>
</ul>
```

-   `<ul>` crea una lista sin numeración.
-   `<li>` representa cada elemento.

## Lista ordenada

Se utiliza cuando el orden sí importa.

``` html
<ol>
    <li>Encender el ordenador</li>
    <li>Abrir el editor</li>
    <li>Crear el archivo HTML</li>
</ol>
```

`<ol>` muestra normalmente números delante de cada elemento.

## Lista de descripción

``` html
<dl>
    <dt>HTML</dt>
    <dd>Lenguaje que define la estructura de una web.</dd>

    <dt>CSS</dt>
    <dd>Lenguaje que define la presentación visual.</dd>
</dl>
```

-   `<dl>` crea la lista de descripciones.
-   `<dt>` indica el término.
-   `<dd>` contiene su explicación.

## Listas anidadas

``` html
<ul>
    <li>Frontend
        <ul>
            <li>HTML</li>
            <li>CSS</li>
        </ul>
    </li>
    <li>Backend</li>
</ul>
```

Una lista puede incluir otra dentro de uno de sus elementos.

# 8. Tablas

Las tablas sirven para mostrar datos relacionados en filas y columnas.
No deben utilizarse para maquetar toda una página.

``` html
<table>
    <caption>Horario del sábado</caption> <!-- Título de la tabla -->

    <thead> <!-- Agrupa la fila de encabezados -->
        <tr> <!-- Crea una fila -->
            <th>Hora</th> <!-- Celda de encabezado -->
            <th>Actividad</th>
        </tr>
    </thead>

    <tbody> <!-- Agrupa los datos -->
        <tr>
            <td>17:00</td> <!-- Celda normal -->
            <td>Apertura de puertas</td>
        </tr>
        <tr>
            <td>18:00</td>
            <td>Concierto</td>
        </tr>
    </tbody>
</table>
```

  Etiqueta    Función
  ----------- ------------------------------------
  `table`     Crea la tabla.
  `caption`   Añade un título o descripción.
  `thead`     Agrupa las filas de encabezado.
  `tbody`     Agrupa el contenido principal.
  `tfoot`     Agrupa el pie de tabla, si existe.
  `tr`        Crea una fila.
  `th`        Crea una celda de encabezado.
  `td`        Crea una celda de datos.

## Unir celdas

``` html
<table>
    <tr>
        <th colspan="2">Información del evento</th>
    </tr>
    <tr>
        <td>Fecha</td>
        <td>14 de agosto</td>
    </tr>
    <tr>
        <td rowspan="2">Lugar</td>
        <td>Playa</td>
    </tr>
    <tr>
        <td>Valencia</td>
    </tr>
</table>
```

-   `colspan="2"` hace que una celda ocupe dos columnas.
-   `rowspan="2"` hace que una celda ocupe dos filas.

## CSS básico para tablas

``` css
table {
    width: 100%;              /* La tabla ocupa todo el ancho disponible */
    border-collapse: collapse;/* Une los bordes de celdas contiguas */
}

th,
td {
    border: 1px solid #999;   /* Añade un borde a cada celda */
    padding: 10px;            /* Separa el texto del borde */
    text-align: left;         /* Alinea el texto a la izquierda */
}

th {
    background-color: #2f5d46; /* Fondo de las cabeceras */
    color: white;              /* Texto blanco */
}
```

# 9. Formularios

Los formularios permiten recoger información del usuario.

``` html
<form action="/procesar" method="post">
    <!-- action indica dónde se enviarían los datos -->
    <!-- method define cómo se envían: get o post -->

    <label for="nombre">Nombre:</label>
    <!-- for debe coincidir con el id del control -->
    <input type="text" id="nombre" name="nombre" required>
    <!-- type text crea una caja de texto -->
    <!-- name identifica el dato enviado -->
    <!-- required obliga a completar el campo -->

    <label for="correo">Correo:</label>
    <input type="email" id="correo" name="correo" required>
    <!-- email comprueba un formato básico de correo -->

    <label for="clave">Contraseña:</label>
    <input type="password" id="clave" name="clave">
    <!-- password oculta visualmente los caracteres -->

    <label for="fecha">Fecha:</label>
    <input type="date" id="fecha" name="fecha">
    <!-- date permite seleccionar una fecha -->

    <label for="mensaje">Mensaje:</label>
    <textarea id="mensaje" name="mensaje" rows="4"></textarea>
    <!-- textarea permite escribir varias líneas -->

    <label for="nivel">Nivel:</label>
    <select id="nivel" name="nivel">
        <option value="facil">Fácil</option>
        <option value="medio">Medio</option>
        <option value="dificil">Difícil</option>
    </select>
    <!-- select crea una lista desplegable -->

    <button type="submit">Enviar</button>
    <!-- submit envía el formulario -->
</form>
```

## Tipos de input frecuentes

  Tipo         Uso
  ------------ ------------------------------------------------------
  `text`       Texto corto.
  `email`      Dirección de correo.
  `password`   Contraseña.
  `number`     Número.
  `date`       Fecha.
  `checkbox`   Casilla que permite marcar varias opciones.
  `radio`      Opción única dentro de un grupo con el mismo `name`.
  `file`       Seleccionar un archivo.
  `submit`     Enviar el formulario.
  `reset`      Restablecer los valores iniciales.

Ejemplo de opciones:

``` html
<p>¿Qué actividades te interesan?</p>
<label><input type="checkbox" name="actividad" value="rutas"> Rutas</label>
<label><input type="checkbox" name="actividad" value="musica"> Música</label>

<p>¿Qué turno prefieres?</p>
<label><input type="radio" name="turno" value="manana"> Mañana</label>
<label><input type="radio" name="turno" value="tarde"> Tarde</label>
```

Los `radio` comparten el mismo `name` para que solo se pueda elegir una
opción del grupo.

**Importante:** HTML crea el formulario, pero para procesar y guardar
los datos normalmente hace falta un servidor o un servicio que reciba el
envío. HTML por sí solo no guarda los datos en una base de datos.

# 10. Estructura semántica de una página

Las etiquetas semánticas describen la función de cada zona de la web.

``` html
<body>
    <header>
        <h1>Club de Senderismo</h1>
        <p>Rutas, amistad y naturaleza</p>
    </header>

    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#rutas">Rutas</a></li>
            <li><a href="#galeria">Galería</a></li>
        </ul>
    </nav>

    <main>
        <section id="inicio">
            <h2>Bienvenidos</h2>
            <p>Salimos a caminar cada fin de semana.</p>
        </section>

        <section id="rutas">
            <h2>Rutas</h2>

            <article>
                <h3>Sendero del Pinar</h3>
                <p>Una ruta sencilla de 6 km.</p>
            </article>
        </section>
    </main>

    <footer>
        <p>© 2026. Todos los derechos reservados.</p>
    </footer>
</body>
```

  -----------------------------------------------------------------------
  Etiqueta                            Función
  ----------------------------------- -----------------------------------
  `header`                            Cabecera de una página o de una
                                      sección.

  `nav`                               Zona que contiene enlaces de
                                      navegación.

  `main`                              Contenido principal de la página.
                                      Normalmente hay uno por documento.

  `section`                           Agrupa contenido relacionado bajo
                                      un tema.

  `article`                           Contenido independiente, como una
                                      noticia, tarjeta o publicación.

  `aside`                             Contenido complementario o lateral.

  `footer`                            Pie de página o de una sección.

  `div`                               Contenedor genérico sin significado
                                      semántico propio.

  `span`                              Contenedor genérico en línea para
                                      fragmentos pequeños.
  -----------------------------------------------------------------------

**Cuándo utilizar `div` y cuándo `section`:** usa `section` cuando el
bloque tenga un tema identificable, normalmente con un encabezado. Usa
`div` cuando solo necesites agrupar elementos para organizarlos o
aplicarles CSS.

# 11. Cómo conectar CSS con HTML

La forma recomendada para los ejercicios es utilizar un archivo CSS
externo.

Estructura del proyecto:

``` text
mi-proyecto/
├── index.html
└── estilos.css
```

Dentro de `<head>` en `index.html`:

``` html
<link rel="stylesheet" href="estilos.css">
<!-- href señala el archivo CSS que debe cargar el navegador -->
```

Ejemplo completo:

``` html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi web</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <h1>Hola, CSS</h1>
</body>
</html>
```

En `estilos.css`:

``` css
h1 {
    color: purple; /* El título se muestra en morado */
}
```

También existen CSS interno (con `<style>` en el HTML) y CSS en línea
(con el atributo `style`), pero el archivo externo facilita mantener el
proyecto ordenado y reutilizar estilos.

# 12. Sintaxis y selectores CSS

Una regla CSS tiene un selector y un bloque de declaraciones.

``` css
p {
    color: #222;       /* Propiedad: color. Valor: #222 */
    font-size: 16px;   /* Propiedad: font-size. Valor: 16px */
}
```

-   `p` es el selector: elige los párrafos.
-   `color` y `font-size` son propiedades.
-   Los valores indican cómo se aplica cada propiedad.
-   Las declaraciones terminan en `;`.
-   Las reglas se escriben entre llaves `{ }`.

## Selector por etiqueta

``` css
h1 {
    color: green; /* Afecta a todos los h1 */
}
```

## Selector por clase

HTML:

``` html
<p class="destacado">Texto importante</p>
```

CSS:

``` css
.destacado {
    background-color: yellow; /* El punto selecciona una clase */
}
```

Una clase se puede repetir en muchos elementos.

## Selector por id

HTML:

``` html
<header id="cabecera">...</header>
```

CSS:

``` css
#cabecera {
    padding: 20px; /* La almohadilla selecciona un id */
}
```

Un `id` debe identificar un único elemento en la página.

## Selector descendiente

``` css
nav a {
    color: white; /* Selecciona enlaces que estén dentro de nav */
}
```

## Selector de varios elementos

``` css
h1,
h2,
h3 {
    font-family: Arial, sans-serif; /* Aplica la misma fuente a los tres */
}
```

## Selector de hijo directo

``` css
nav > ul {
    list-style: none; /* Selecciona ul que sea hijo directo de nav */
}
```

## Selector universal

``` css
* {
    box-sizing: border-box; /* Se aplica a todos los elementos */
}
```

`box-sizing: border-box` hace que el ancho y alto declarados incluyan
padding y border, lo que facilita calcular tamaños.

# 13. Colores, fondos y tipografía

## Colores

``` css
body {
    color: #222222;            /* Color del texto */
    background-color: #eeeeee; /* Color del fondo */
}
```

Formas habituales de escribir colores:

``` css
h1 { color: red; }                  /* Nombre del color */
p { color: #ff4f81; }              /* Hexadecimal */
.destacado { color: rgb(255, 79, 129); } /* RGB */
.tarjeta { background-color: rgba(0, 0, 0, 0.5); } /* RGB con transparencia */
```

En `rgba`, el cuarto valor es la opacidad: `0` es transparente y `1` es
opaco.

## Fondo

``` css
body {
    background-color: #f2f2f2; /* Fondo de un color */
}

.portada {
    background-image: url("imagenes/fondo.jpg"); /* Imagen de fondo */
    background-size: cover;       /* Cubre el bloque, recortando si hace falta */
    background-position: center;  /* Centra la imagen */
    background-repeat: no-repeat; /* Evita repetirla */
}
```

## Tipografía

``` css
body {
    font-family: Arial, sans-serif; /* Fuente principal y alternativa genérica */
    font-size: 16px;                /* Tamaño base */
    line-height: 1.6;                /* Altura de línea; mejora la lectura */
}

h1 {
    font-size: 32px;       /* Tamaño del encabezado */
    font-weight: bold;     /* Grosor de la letra */
    text-align: center;    /* Alineación centrada */
    text-transform: uppercase; /* Convierte visualmente a mayúsculas */
}
```

Propiedades habituales:

-   `font-family`: familia tipográfica.
-   `font-size`: tamaño.
-   `font-weight`: grosor.
-   `font-style`: estilo, por ejemplo `italic`.
-   `line-height`: separación vertical entre líneas.
-   `text-align`: alineación del texto.
-   `text-decoration`: subrayado, tachado o eliminación de decoración.
-   `text-transform`: transformación visual a mayúsculas/minúsculas.
-   `letter-spacing`: separación entre letras.

## Importar una fuente externa

Ejemplo con Google Fonts:

``` css
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700&display=swap');

body {
    font-family: 'Nunito', sans-serif; /* Utiliza Nunito y deja sans-serif como alternativa */
}
```

La regla `@import` se coloca al principio del archivo CSS, antes de las
reglas normales. También se puede cargar la fuente mediante un enlace
`<link>` en el HTML.

# 14. El modelo de caja: margin, border y padding

Cada elemento HTML se representa como una caja. Sus partes principales
son:

-   **Contenido:** texto, imagen u otros elementos.
-   **Padding:** espacio interior entre el contenido y el borde.
-   **Border:** línea que rodea el padding y el contenido.
-   **Margin:** espacio exterior que separa esta caja de otras.

``` css
.tarjeta {
    width: 300px;             /* Ancho del contenido, con content-box */
    padding: 20px;            /* Espacio interior en los cuatro lados */
    border: 2px solid black;  /* Borde de 2 px, continuo y negro */
    margin: 15px;             /* Separación exterior de 15 px */
}
```

## Escribir los cuatro lados

``` css
.caja {
    margin-top: 10px;     /* Margen superior */
    margin-right: 20px;   /* Margen derecho */
    margin-bottom: 10px;  /* Margen inferior */
    margin-left: 20px;    /* Margen izquierdo */

    padding: 10px 20px;   /* 10 px arriba/abajo y 20 px izquierda/derecha */
}
```

También se puede usar la forma abreviada:

``` css
.caja {
    margin: 10px 20px 30px 40px;
    /* Orden: arriba, derecha, abajo, izquierda (sentido horario) */
}
```

## Centrar un contenedor

``` css
.contenedor {
    width: 960px;       /* Ancho fijo */
    margin: 0 auto;     /* 0 arriba/abajo y automático a izquierda/derecha */
}
```

`margin: 0 auto` centra horizontalmente un bloque que tenga un ancho
definido o limitado.

## Bordes redondeados y sombras

``` css
.tarjeta {
    border: 1px solid #ccc;          /* Borde fino */
    border-radius: 12px;             /* Esquinas redondeadas */
    box-shadow: 0 4px 12px rgba(0,0,0,0.15); /* Sombra exterior */
}
```

# 15. Tamaños y visualización: width, height y display

## Dimensiones

``` css
.caja {
    width: 300px;      /* Anchura */
    height: 200px;     /* Altura */
    max-width: 100%;   /* No supera el ancho disponible */
    min-height: 100px; /* No baja de esa altura */
}
```

Unidades frecuentes:

-   `px`: píxeles CSS.
-   `%`: porcentaje del tamaño del contenedor.
-   `em`: relativo al tamaño de fuente del elemento.
-   `rem`: relativo al tamaño de fuente raíz.
-   `vh`: porcentaje de la altura de la ventana.
-   `vw`: porcentaje del ancho de la ventana.

## display

`display` determina cómo participa un elemento en la distribución de la
página.

``` css
.bloque {
    display: block; /* Empieza en una línea nueva y ocupa el ancho disponible */
}

.en-linea {
    display: inline; /* Comparte línea; width y height no se aplican como en un bloque */
}

.tarjeta {
    display: inline-block; /* Se coloca en línea y permite definir width y height */
}

.oculto {
    display: none; /* No se muestra y no reserva espacio en el diseño */
}
```

Ejemplos:

-   `block`: habitual en `div`, `p`, `section`.
-   `inline`: habitual en `span`, `a`, `strong`.
-   `inline-block`: útil para colocar tarjetas en fila manteniendo
    dimensiones.
-   `none`: oculta el elemento y lo retira del flujo de diseño.

## Tarjetas en línea con inline-block

``` html
<div class="tarjeta">Tarjeta 1</div>
<div class="tarjeta">Tarjeta 2</div>
<div class="tarjeta">Tarjeta 3</div>
```

``` css
.tarjeta {
    display: inline-block; /* Coloca las tarjetas una junto a otra */
    width: 270px;          /* Ancho de cada tarjeta */
    vertical-align: top;  /* Alinea las tarjetas por su parte superior */
}
```

Puede aparecer un pequeño espacio entre elementos `inline-block` debido
a los espacios o saltos de línea del HTML.

# 16. Listas y formularios con CSS

## Quitar las viñetas de una lista de navegación

``` css
nav ul {
    list-style: none; /* Elimina puntos o números */
    margin: 0;         /* Quita margen predeterminado */
    padding: 0;        /* Quita sangría interior predeterminada */
}

nav li {
    display: inline-block; /* Coloca los elementos del menú en una fila */
    margin-right: 15px;    /* Separa los enlaces */
}
```

## Cambiar el aspecto de una lista

``` css
.horario {
    list-style: none; /* Quita las viñetas normales */
    padding-left: 20px;
}

.horario li {
    padding: 12px;                 /* Espacio interior */
    border-bottom: 1px solid #ddd; /* Línea separadora */
}
```

## Estilizar formularios

``` css
form {
    max-width: 500px; /* Limita el ancho del formulario */
}

label {
    display: block;   /* Cada etiqueta ocupa su propia línea */
    margin-top: 12px; /* Separa los campos */
}

input,
textarea,
select {
    width: 100%;       /* Ocupan el ancho disponible */
    padding: 10px;     /* Espacio interior */
    border: 1px solid #aaa;
    border-radius: 5px;
    box-sizing: border-box; /* El padding y el borde se incluyen en el ancho */
}

button {
    margin-top: 15px;
    padding: 10px 18px;
    background-color: #2f5d46;
    color: white;
    border: 0;
    cursor: pointer; /* Muestra el cursor de mano */
}
```

# 17. Agrupación de elementos con div y span

`div` y `span` no aportan significado específico: sirven como
contenedores genéricos.

``` html
<div class="tarjeta">
    <h2>Sendero del Pinar</h2>
    <p>Nivel: <span class="nivel">Fácil</span></p>
</div>
```

-   `div.tarjeta` agrupa la información de la tarjeta.
-   `span.nivel` permite dar estilo solo a la palabra «Fácil».

``` css
.tarjeta {
    background-color: #f4f4f4; /* Fondo de toda la tarjeta */
    padding: 20px;
}

.nivel {
    color: green; /* Solo cambia el fragmento dentro del span */
    font-weight: bold;
}
```

## Agrupar tarjetas con section y article

``` html
<section id="rutas">
    <h2>Rutas disponibles</h2>

    <article class="ruta">
        <h3>Sendero del Pinar</h3>
        <p>Ruta fácil de 6 km.</p>
    </article>

    <article class="ruta">
        <h3>Cresta del Mirador</h3>
        <p>Ruta de nivel medio.</p>
    </article>
</section>
```

La sección agrupa el tema «Rutas» y cada `article` representa una ruta
independiente.

# 18. Pseudoclases y pseudoelementos

## :hover

`:hover` aplica estilos cuando el puntero está encima de un elemento.

``` css
nav a {
    color: white;
    text-decoration: none;
}

nav a:hover {
    color: orange; /* El enlace cambia al pasar el ratón */
}
```

## :nth-child()

`:nth-child()` selecciona elementos según su posición entre los
hermanos.

``` css
article:nth-child(1) {
    background-color: #a2b3bc; /* Primer article */
}

article:nth-child(2) {
    background-color: #f1974f; /* Segundo article */
}

article:nth-child(3) {
    background-color: #d03d6b; /* Tercer article */
}
```

También admite patrones:

``` css
li:nth-child(even) {
    background-color: #eee; /* Elementos pares */
}

li:nth-child(odd) {
    background-color: white; /* Elementos impares */
}
```

La posición cuenta entre los hermanos del mismo tipo de relación; hay
que revisar la estructura HTML para saber qué elemento ocupa cada
puesto.

## Otras pseudoclases

``` css
a:visited { color: purple; }      /* Enlace visitado */
input:focus { border-color: blue; } /* Campo que tiene el foco */
li:first-child { font-weight: bold; } /* Primer hijo */
li:last-child { color: red; }      /* Último hijo */
```

## Pseudoelementos ::before y ::after

Permiten insertar contenido decorativo desde CSS.

``` css
.aviso::before {
    content: "★ "; /* Inserta una estrella antes del contenido */
}

.aviso::after {
    content: " ✓"; /* Inserta un símbolo después */
}
```

Para crear una línea decorativa:

``` css
.horario {
    position: relative; /* Se convierte en referencia para el pseudoelemento */
}

.horario::before {
    content: "";             /* Necesario para crear el elemento decorativo */
    position: absolute;      /* Permite colocarlo dentro del contenedor */
    left: 8px;               /* Distancia desde la izquierda */
    top: 0;
    bottom: 0;
    width: 2px;              /* Grosor de la línea */
    background-color: orange;
}
```

El pseudoelemento es decorativo: no sustituye al contenido HTML ni debe
utilizarse para información imprescindible.

# 19. Transformaciones y transiciones

## transform: scale()

Aumenta o reduce visualmente el tamaño de un elemento.

``` css
.logo {
    transition: transform 0.3s ease; /* Anima el cambio durante 0,3 segundos */
}

.logo:hover {
    transform: scale(1.15); /* Aumenta el tamaño un 15 % al pasar el ratón */
}
```

## Otras transformaciones

``` css
.caja:hover {
    transform: translateY(-5px); /* Desplaza visualmente 5 px hacia arriba */
}

.imagen:hover {
    transform: rotate(3deg); /* Gira 3 grados */
}
```

-   `scale()` cambia la escala.
-   `translate()` desplaza.
-   `rotate()` gira.
-   `skew()` inclina.

## transition

`transition` suaviza el cambio entre estados.

``` css
.boton {
    background-color: green;
    transform: scale(1);
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.boton:hover {
    background-color: darkgreen;
    transform: scale(1.05);
}
```

La transición se declara normalmente en el estado inicial, para que el
cambio al entrar y salir de `:hover` sea suave.

# 20. Posicionamiento CSS

La propiedad `position` determina cómo se coloca un elemento. En las
actividades se deben conocer los cinco valores: `static`, `relative`,
`absolute`, `fixed` y `sticky`.

## 20.1 position: static

``` css
.elemento {
    position: static; /* Posición normal del documento; es el valor predeterminado */
}
```

-   El elemento sigue el flujo normal de la página.
-   `top`, `right`, `bottom` y `left` no desplazan un elemento estático.
-   Se utiliza cuando no se necesita un posicionamiento especial.

## 20.2 position: relative

``` css
.tarjeta {
    position: relative; /* Mantiene su espacio original y permite desplazarla */
    top: -12px;          /* La mueve 12 px hacia arriba */
}
```

-   El elemento conserva el espacio que ocupaba originalmente.
-   Puede desplazarse usando `top`, `right`, `bottom` y `left`.
-   También sirve como referencia para elementos hijos con
    `position: absolute`.

Ejemplo: elevar una tarjeta central sin mover las tarjetas vecinas.

``` css
.tarjeta-central {
    position: relative;
    top: -12px; /* Sube visualmente 12 px */
    box-shadow: 0 5px 12px rgba(0, 0, 0, 0.2);
}
```

## 20.3 position: absolute

``` css
.cabecera {
    position: relative; /* Establece el contexto de posicionamiento */
}

.sello {
    position: absolute; /* Sale del flujo normal */
    top: 16px;           /* A 16 px del borde superior de la cabecera */
    right: 16px;         /* A 16 px del borde derecho de la cabecera */
}
```

-   El elemento absoluto sale del flujo normal: los demás elementos no
    reservan su espacio.
-   Se coloca respecto al antecesor posicionado más cercano.
-   Por eso suele ponerse `position: relative` en el contenedor padre.
-   Si no encuentra un antecesor adecuado, puede posicionarse respecto
    al bloque inicial de la página.

**Regla para recordar:** padre `relative` + hijo `absolute` permite
colocar el hijo en una esquina del padre.

## 20.4 position: fixed

``` css
.boton-subir {
    position: fixed; /* Se fija respecto a la ventana del navegador */
    right: 20px;     /* A 20 px del borde derecho */
    bottom: 20px;    /* A 20 px del borde inferior */
}
```

-   Permanece en el mismo lugar de la ventana aunque se haga scroll.
-   No reserva su espacio en el flujo normal.
-   Es útil para botones flotantes o menús laterales permanentes.

Menú lateral fijo:

``` css
nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 200px;
    height: 100vh; /* 100 % de la altura de la ventana */
}

main {
    margin-left: 220px; /* Evita que el contenido quede debajo del menú */
}
```

## 20.5 position: sticky

``` css
nav {
    position: sticky; /* Se comporta normalmente hasta alcanzar el límite */
    top: 0;            /* Se queda pegado al llegar a la parte superior */
    z-index: 10;       /* Lo coloca por encima del contenido que pasa detrás */
}
```

-   Se comporta como un elemento normal hasta alcanzar el umbral
    indicado.
-   Después se queda pegado dentro de los límites de su contenedor.
-   Necesita un valor de referencia, normalmente `top`.
-   Puede no funcionar como se espera si algún contenedor superior tiene
    `overflow` que cambia su área de desplazamiento.

Ejemplo para títulos de sección:

``` css
section h2 {
    position: sticky;
    top: 0;
    z-index: 5;
    background-color: white; /* Evita que se vea el texto por detrás */
    padding: 12px;
}
```

## Comparación rápida

  -----------------------------------------------------------------------
  Valor             ¿Conserva su      ¿Se mueve con el  Uso habitual
                    espacio?          scroll?           
  ----------------- ----------------- ----------------- -----------------
  `static`          Sí                Sí, como el       Diseño normal.
                                      contenido normal  

  `relative`        Sí                Sí, como el       Desplazamiento
                                      contenido normal  pequeño o
                                                        referencia para
                                                        hijos absolutos.

  `absolute`        No                Sí, con su bloque Sello, etiqueta
                                      de referencia     sobre una
                                                        tarjeta.

  `fixed`           No                No, queda fijo en Botón flotante o
                                      la ventana        menú lateral
                                                        fijo.

  `sticky`          Sí                Se pega al        Menú superior o
                                      alcanzar un       títulos de
                                      límite            sección.
  -----------------------------------------------------------------------

# 21. Overflow, z-index y scroll

## overflow

Controla qué ocurre cuando el contenido supera el tamaño de una caja.

``` css
.caja {
    width: 300px;
    height: 170px;
    overflow: auto; /* Muestra barras solo cuando son necesarias */
}
```

Valores:

-   `visible`: el contenido puede sobresalir; es el comportamiento
    habitual.
-   `hidden`: recorta lo que sobresale.
-   `scroll`: muestra barras de desplazamiento.
-   `auto`: muestra barras cuando hacen falta.

Ejemplo de caja de opiniones:

``` css
.opiniones {
    height: 170px;       /* Altura fija */
    overflow-y: auto;   /* Permite desplazarse verticalmente */
    overflow-x: hidden; /* Oculta el desbordamiento horizontal */
}
```

## z-index

Controla qué elemento aparece por delante cuando hay elementos
superpuestos.

``` css
.tarjeta {
    position: relative;
    z-index: 1;
}

.tarjeta-central {
    position: relative;
    z-index: 2; /* Se muestra por delante de las tarjetas con z-index menor */
}
```

`z-index` suele funcionar en elementos posicionados y también en
determinados contextos de diseño. Un valor mayor no siempre supera
cualquier otro: los contextos de apilamiento pueden limitar la
comparación.

## Recortar el contenido de una tarjeta

``` css
.tarjeta {
    position: relative; /* Referencia para la etiqueta absoluta */
    overflow: hidden;   /* Recorta lo que sobresalga */
}

.etiqueta {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

# 22. Ejemplos completos inspirados en las actividades

Esta sección reúne patrones presentes en las actividades adjuntas. Los
ejemplos son modelos didácticos: se pueden adaptar a los nombres, textos
y colores que pida cada ejercicio.

## 22.1 Actividad de redes sociales: estructura y tarjetas

HTML:

``` html
<header>
    <h1>Mis redes sociales</h1>
</header>

<nav>
    <a href="#redes">Redes</a>
    <a href="#contacto">Contacto</a>
</nav>

<main>
    <section id="redes">
        <h2>Encuéntrame en redes</h2>

        <article class="red facebook">
            <h3>Facebook</h3>
            <img src="imagenes/facebook.png" alt="Icono de Facebook">
        </article>

        <article class="red twitter">
            <h3>Twitter</h3>
            <img src="imagenes/twitter.png" alt="Icono de Twitter">
        </article>

        <article class="red youtube">
            <h3>YouTube</h3>
            <img src="imagenes/youtube.png" alt="Icono de YouTube">
        </article>
    </section>
</main>

<footer>
    <p>© 2026. Mi web.</p>
</footer>
```

CSS:

``` css
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700&display=swap');

body {
    font-family: 'Nunito', sans-serif; /* Importa y utiliza Nunito */
    margin: 0;                         /* Elimina margen predeterminado */
}

header,
nav,
footer {
    background-color: #eeeeee; /* Fondo común de cabecera, menú y pie */
    padding: 20px;
}

.red {
    display: inline-block; /* Coloca las tarjetas en línea */
    width: 180px;
    padding: 15px;
}

.facebook { background-color: rgba(162, 179, 188, 0.5); }
.twitter  { background-color: rgba(241, 151, 79, 0.5); }
.youtube  { background-color: rgba(208, 61, 107, 0.5); }

nav a:hover {
    color: red;                  /* Texto rojo al pasar el ratón */
    border-top: 2px solid red;   /* Borde superior */
    border-bottom: 2px solid red;/* Borde inferior */
}

.red img {
    width: 80px;
    transition: transform 0.3s ease; /* Prepara la animación */
}

.red img:hover {
    transform: scale(1.2); /* Agranda el icono al pasar el ratón */
}
```

Conceptos practicados: etiquetas semánticas, `section`, `article`,
`inline-block`, importación de fuente, colores `rgba`, `:hover`,
`transform` y `transition`.

## 22.2 Actividad de posicionamiento: Club de Senderismo Monte Verde

HTML:

``` html
<div class="contenedor">
    <header id="arriba">
        <h1>Club de Senderismo Monte Verde</h1>
        <p>Rutas, amistad y naturaleza</p>
        <span class="sello">Nueva temporada</span>
    </header>

    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#rutas">Rutas</a></li>
            <li><a href="#galeria">Galería</a></li>
            <li><a href="#opiniones">Opiniones</a></li>
        </ul>
    </nav>

    <main>
        <section id="inicio">
            <h2>Inicio</h2>
            <p>Somos un grupo de amigos que sale a caminar cada fin de semana.</p>
        </section>

        <section id="rutas">
            <h2>Rutas</h2>

            <article class="ruta">
                <div class="foto"></div>
                <span class="nivel">Fácil</span>
                <h3>Sendero del Pinar</h3>
                <p>6 km por pista forestal sombreada.</p>
            </article>

            <article class="ruta central">
                <div class="foto"></div>
                <span class="nivel">Media</span>
                <h3>Cresta del Mirador</h3>
                <p>11 km con vistas a toda la sierra.</p>
            </article>

            <article class="ruta">
                <div class="foto"></div>
                <span class="nivel">Difícil</span>
                <h3>Barranco Hondo</h3>
                <p>15 km de recorrido exigente.</p>
            </article>
        </section>

        <section id="galeria">
            <h2>Galería</h2>
            <div class="polaroid">Amanecer en la cresta</div>
            <div class="polaroid central">Descanso junto al río</div>
            <div class="polaroid">Cima de la sierra</div>
        </section>

        <section id="opiniones">
            <h2>Opiniones</h2>
            <div class="opiniones">
                <article><p>Marta: una experiencia estupenda.</p></article>
                <article><p>Luis: rutas muy bien organizadas.</p></article>
                <article><p>Carmen: repetiré la próxima semana.</p></article>
                <article><p>Pablo: buen ambiente.</p></article>
                <article><p>Inés: paisajes preciosos.</p></article>
                <article><p>Raúl: recomendable.</p></article>
            </div>
        </section>
    </main>
</div>

<footer>
    <p>© 2026. Tu nombre y apellidos.</p>
    <a class="subir" href="#arriba">↑ Subir</a>
</footer>
```

CSS:

``` css
body {
    margin: 0;
    background-color: #e9efe9; /* Fondo verde muy claro */
    color: #222;
    font-family: Arial, sans-serif;
}

.contenedor {
    width: 960px;
    margin: 0 auto; /* Centra el contenedor */
    background-color: white;
}

header {
    position: relative; /* Referencia del sello absoluto */
    padding: 30px;
    background-color: #2f5d46;
    color: white;
}

.sello {
    position: absolute;
    top: 16px;
    right: 16px;
    width: 84px;
    height: 84px;
    border-radius: 50%; /* Convierte el bloque cuadrado en círculo */
    background-color: #f08a24;
}

nav {
    position: sticky;
    top: 0;
    z-index: 10; /* Mantiene el menú por encima del contenido */
    background-color: #2f5d46;
}

nav li {
    display: inline-block;
    padding: 12px;
}

nav a {
    color: white;
    text-decoration: none;
}

nav a:hover {
    color: #f08a24;
}

.ruta {
    position: relative; /* Referencia de la etiqueta de nivel */
    display: inline-block;
    vertical-align: top;
    width: 270px;
    overflow: hidden; /* Recorta lo que sobresale */
    background-color: #f4f4f4;
}

.foto {
    height: 120px;
    background-color: #8fb996;
}

.nivel {
    position: absolute;
    top: 10px;
    right: 10px;
    background-color: #f08a24;
    border-radius: 20px;
    padding: 5px 10px;
}

.ruta.central {
    position: relative;
    top: -12px; /* Se eleva sin desplazar a sus vecinas */
    box-shadow: 0 5px 12px rgba(0,0,0,0.2);
}

.polaroid {
    position: relative;
    display: inline-block;
    width: 280px;
    height: 210px;
    border: 6px solid white;
    background-color: #a7c5d9;
    z-index: 1;
}

.polaroid.central {
    z-index: 2; /* La central aparece por delante */
}

.polaroid:hover {
    z-index: 3; /* La polaroid señalada pasa al frente */
}

.opiniones {
    height: 170px;
    overflow-y: auto; /* Desplazamiento vertical */
}

.subir {
    position: fixed;
    right: 20px;
    bottom: 20px;
}
```

**Qué debes identificar en este ejercicio:**

-   `relative` en la cabecera crea la referencia para el sello.
-   `absolute` coloca el sello dentro de la cabecera.
-   `sticky` mantiene el menú pegado arriba durante el desplazamiento.
-   `relative` desplaza la tarjeta central sin quitar su espacio
    original.
-   `z-index` decide qué polaroid queda delante.
-   `overflow-y: auto` permite recorrer las opiniones dentro de una
    altura fija.
-   `fixed` mantiene el botón «Subir» en la ventana.

## 22.3 Actividad Festival Mar Sonora: menú lateral y línea de tiempo

HTML:

``` html
<nav class="menu-lateral">
    <p>MAR SONORA</p>
    <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#programa">Programa</a></li>
        <li><a href="#artistas">Artistas</a></li>
        <li><a href="#info">Info</a></li>
    </ul>
</nav>

<main>
    <header id="inicio">
        <div class="portada">
            <h1>Festival Mar Sonora</h1>
            <p>14 y 15 de agosto · Playa de la Malvarrosa, Valencia</p>
        </div>
    </header>

    <section id="programa">
        <h2>Programa del sábado</h2>
        <ul class="horario">
            <li><strong>17:00</strong> Apertura de puertas y DJ de bienvenida</li>
            <li><strong>18:00</strong> Los Faroles (pop-rock)</li>
            <li><strong>19:15</strong> Marea Alta (indie)</li>
            <li><strong>20:30</strong> Puesta de sol con Laia Verd</li>
            <li><strong>21:45</strong> Cabeza de cartel: Delta 66</li>
            <li><strong>23:15</strong> Sesión electrónica de Nora K</li>
            <li><strong>01:00</strong> Cierre y after en la arena</li>
        </ul>
    </section>

    <section id="artistas">
        <h2>Artistas</h2>
        <div class="cartel">
            <span>Delta 66</span>
            <span>Nora K</span>
            <span>Marea Alta</span>
            <span>Laia Verd</span>
            <span>Los Faroles</span>
            <span>DJ Brisa</span>
            <span>Costa Norte</span>
            <span>Las Gaviotas</span>
        </div>
    </section>

    <section id="info">
        <h2>Info útil</h2>
        <div class="faq">
            <p><strong>¿Hay aparcamiento?</strong> Hay zonas de aparcamiento cercanas.</p>
            <p><strong>¿Puedo entrar con comida?</strong> Consulta las condiciones de acceso.</p>
            <p><strong>¿Hay consigna?</strong> Sí, habrá un espacio habilitado.</p>
            <p><strong>¿Se puede pagar con tarjeta?</strong> Sí, en los puestos habilitados.</p>
            <p><strong>¿Edad mínima?</strong> Revisa las condiciones de acceso del evento.</p>
            <p><strong>¿Y si llueve?</strong> Se comunicará cualquier cambio por los canales oficiales.</p>
        </div>
    </section>

    <footer>© 2026. Tu nombre y apellidos.</footer>
</main>
```

CSS:

``` css
* {
    box-sizing: border-box; /* Incluye padding y borde en las dimensiones */
}

body {
    margin: 0;
    background-color: #111; /* Fondo casi negro */
    color: #f5f5f5;         /* Texto claro */
    font-family: Arial, sans-serif;
}

.menu-lateral {
    position: fixed; /* Permanece fijo al hacer scroll */
    top: 0;
    left: 0;
    width: 200px;
    height: 100vh; /* Toda la altura de la ventana */
    padding: 20px;
    background-color: #202020;
}

.menu-lateral a {
    color: white;
    text-decoration: none;
}

.menu-lateral a:hover {
    color: #ff4f81;
}

main {
    margin-left: 200px; /* Deja sitio al menú fijo */
    padding: 20px;
}

header {
    position: relative; /* Referencia para la portada */
    height: 300px;
    background-color: #333;
}

.portada {
    position: absolute;
    left: 30px;
    bottom: 30px; /* Coloca título y subtítulo abajo a la izquierda */
}

section h2 {
    position: sticky;
    top: 0;
    z-index: 5;
    padding: 12px;
    background-color: #222; /* Fondo opaco para tapar el contenido que pasa detrás */
}

.horario {
    position: relative; /* Referencia para la línea temporal */
    list-style: none;
    padding-left: 30px;
}

.horario::before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    left: 8px;
    width: 2px;
    background-color: #38e1d0; /* Línea vertical */
}

.horario li {
    position: relative; /* Referencia del punto de cada evento */
    padding: 12px 0;
}

.horario li::before {
    content: "";
    position: absolute;
    left: -27px;
    top: 18px;
    width: 12px;
    height: 12px;
    border-radius: 50%; /* Punto circular */
    background-color: #ff4f81;
}

.cartel span {
    display: inline-block;
    margin: 6px;
    padding: 10px 16px;
    border: 1px solid #38e1d0;
    border-radius: 30px; /* Forma de píldora */
}

.cartel span:first-child {
    background-color: #ff4f81; /* Destaca el primer artista */
}

.faq {
    height: 170px;
    overflow-y: auto; /* Permite recorrer las preguntas y respuestas */
    padding: 12px;
    border: 1px solid #38e1d0;
}

footer {
    padding: 20px;
    border-top: 1px solid #444;
}
```

**Qué debes identificar en este ejercicio:**

-   El menú lateral usa `fixed`, ocupa `100vh` y tiene `width: 200px`.
-   `main` usa `margin-left` para no quedar oculto debajo del menú.
-   La portada es un bloque de `300px`; el contenido se coloca con
    `absolute`.
-   Los títulos de sección utilizan `sticky` y un fondo opaco.
-   `::before` crea la línea vertical y los puntos de la línea de
    tiempo.
-   Los artistas son `span` con `inline-block` y `border-radius`.
-   El bloque de preguntas tiene altura fija y `overflow-y: auto`.

# 23. Errores frecuentes

1.  **El CSS no se aplica.** Comprueba que el nombre del archivo y la
    ruta de `href` sean correctos.
2.  **Una imagen no aparece.** Revisa el nombre, la extensión y la ruta
    de `src`. Las mayúsculas y minúsculas pueden importar según el
    servidor.
3.  **Un enlace interno no funciona.** Comprueba que `href="#seccion"`
    coincida con `id="seccion"`.
4.  **El elemento absoluto aparece en una esquina inesperada.** Añade
    `position: relative` al contenedor que debe servirle de referencia.
5.  **Sticky no se queda pegado.** Comprueba que tiene `top` y revisa el
    `overflow` de sus contenedores.
6.  **El botón fixed tapa contenido.** Ajusta su posición o reserva
    espacio para que no tape información importante.
7.  **El z-index parece no funcionar.** Revisa si los elementos crean
    contextos de apilamiento diferentes.
8.  **Las tarjetas inline-block no encajan.** Comprueba sus anchos, el
    espacio entre ellas y el ancho disponible del contenedor.
9.  **La caja no muestra scroll.** Comprueba que tenga una altura o
    anchura limitada y que el contenido realmente desborde.
10. **El formulario no envía lo esperado.** Revisa `name`, `action`,
    `method` y el mecanismo que recibe los datos.
11. **El HTML queda desordenado.** Revisa que las etiquetas estén
    correctamente anidadas y cerradas.
12. **Se utiliza un h1 solo por su tamaño.** Elige encabezados por
    jerarquía y cambia su apariencia con CSS.

# 24. Checklist antes de entregar en GitHub

-   [ ] El archivo principal se llama `index.html`.
-   [ ] El archivo de estilos se llama `estilos.css`.
-   [ ] El HTML incluye `<!DOCTYPE html>`, `lang`, `charset` y
    `viewport`.
-   [ ] El CSS externo está enlazado correctamente.
-   [ ] Las etiquetas están bien anidadas y cerradas.
-   [ ] Las imágenes tienen rutas correctas y texto `alt`.
-   [ ] Los enlaces externos e internos funcionan.
-   [ ] Los `id` no están repetidos.
-   [ ] Las clases están escritas igual en HTML y CSS.
-   [ ] Se han revisado colores, márgenes, padding, bordes y tamaños.
-   [ ] Se ha probado el comportamiento de `:hover`.
-   [ ] Se han comprobado los cinco valores de `position` cuando el
    ejercicio lo exige.
-   [ ] Se ha revisado `z-index` en elementos superpuestos.
-   [ ] Se ha comprobado el scroll de las cajas con `overflow`.
-   [ ] La página se ha probado en el navegador y al cambiar el tamaño
    de ventana.
-   [ ] El repositorio contiene los archivos solicitados y, si
    corresponde, la carpeta de imágenes.

------------------------------------------------------------------------

## Nota final

Esta guía explica los conceptos generales de HTML y CSS y recoge los
requisitos y patrones de las actividades facilitadas. Los textos de
ejemplo y algunos valores CSS son ilustrativos; cuando una actividad
indique colores, medidas, nombres o contenidos concretos, utiliza los
que pida esa actividad.

**Consejo:** escribe primero la estructura HTML, comprueba que el
contenido aparece correctamente y después añade CSS por bloques. Así
será más fácil localizar errores.
