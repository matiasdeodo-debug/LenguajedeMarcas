# HTML + CSS: reparar una página

🟥 = HTML · 🟦 = CSS · 🟨 = truco · ✅ = arreglo

---

## 1. Método (siempre igual)

1. Abrir con **Live Server** y mirar la página entera. Lo que se vea raro es un error.
2. Pulsar **F12** → *Console* y *Network*: si un archivo no carga sale en rojo con su ruta.
3. Revisar el `<head>`: charset, `<link>` al CSS bien escrito.
4. Leer el CSS de arriba abajo con las tablas de abajo al lado.
5. Arreglar **uno**, guardar (Ctrl+S), comprobar. Luego el siguiente.

🟨 Validar el HTML en https://validator.w3.org (te dice la línea del fallo).
🟨 En VS Code, si una propiedad CSS no se pone de color, está mal escrita.

---

## 2. Esqueleto base

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Título</title>
  <link rel="stylesheet" href="estilos.css">
</head>
<body>
  <header></header>
  <nav></nav>
  <section></section>
  <footer></footer>
</body>
</html>
```

---

## 3. 🟥 Errores de HTML

| Qué se ve | Causa | ✅ Arreglo |
|---|---|---|
| Símbolos raros (Ã±, Ã³) | Falta `<meta charset="utf-8">` | Ponerlo en el `<head>` |
| Página sin estilos | `<link>` mal: nombre, ruta o falta `rel="stylesheet"` | Copiar el nombre exacto (las mayúsculas cuentan) |
| Imagen rota | Ruta mala en `src` | Mismo carpeta: `src="logo.png"` · en carpeta img: `src="img/logo.png"` · subir una carpeta: `../logo.png` |
| Falta `alt` | Se olvidó | `alt="descripción de la imagen"` |
| Todo descuadrado | Etiqueta sin cerrar o mal cerrada (`<h2>..</h3>`, falta `</tr>`) | Cerrar en orden: la última que abres es la primera que cierras |
| Enlace interno no salta | `href="#contactos"` pero el id es `contacto` | Iguales letra por letra (`#` solo en el href) |
| Dos elementos con el mismo id | Un id solo se usa una vez | Usar `class` si se repite |
| Al pulsar el label no pasa nada | `for` distinto del `id` del input | `<label for="x">` + `<input id="x">` |
| Campo de correo no valida | `type="mail"` | `type="email"` (otros: text, password, number, tel, date) |
| Formulario sin botón | Falta | `<button type="submit">Enviar</button>` |
| Cosas fuera de su sitio | `<li>` fuera de `<ul>`, `<td>` fuera de `<tr>` | `ul > li` · `table > tr > td` |
| Falta `<!DOCTYPE html>` o `lang` | Se olvidó | Ponerlos |
| Se come texto con `<` o `&` | Son símbolos de HTML | `&lt;` `&gt;` `&amp;` |
| Atributo roto | Falta una comilla: `class="tarjeta` | Abrir y cerrar `"..."` |

---

## 4. 🟦 Errores de CSS

| Qué pasa | Causa | ✅ Arreglo |
|---|---|---|
| Una regla no hace nada | El selector no coincide con el HTML | `.clase` para class, `#id` para id, sin nada para etiqueta |
| Una propiedad no funciona | Mal escrita: `colour`, `text-allign`, `font-wieght` | `color`, `text-align`, `font-weight` |
| Fallan dos propiedades seguidas | Falta `;` | Cada propiedad termina en `;` |
| `padding: 20` no hace nada | Falta la unidad | `20px` (solo el `0` va sin unidad) |
| Falla todo lo que hay debajo | Falta `}` o `:` | Cerrar cada regla con `}` |
| Color no sale | Hex con dígitos mal: `#E0A52` | 3 o 6 dígitos con `#`: `#E0A526` |
| Se rompe la regla de debajo | Comentario con `//` | En CSS: `/* comentario */` |
| `::before` / `::after` no se ve | Falta `content` (o sin comillas) | `content: "★";` (aunque sea `""`) |
| El hover no pasa | `:hober`, `tr:nth-child(even {` | `:hover`, `tr:nth-child(even) {` |
| Un elemento se va a la esquina de la página | `absolute` sin padre `relative` | Al padre: `position: relative;` |
| El menú no se queda arriba | `sticky` sin `top` | `position: sticky; top: 0;` |
| El botón se mueve con el scroll | Es `absolute` | `position: fixed;` |
| No se ven las filas de abajo | `overflow: hidden` | `overflow-y: auto;` |
| Un elemento queda tapado | `z-index` bajo o sin `position` | `position: relative; z-index: 10;` |
| Las tarjetas se bajan de línea | width + padding + border + margin suman más que el contenedor | Achicar `width` o `box-sizing: border-box;` |
| No se centra | Falta ancho | `width: 900px; margin: 0 auto;` |
| No se ve bien en el móvil | `width` fijo | `max-width: 900px; width: 100%;` y el meta viewport |
| Mi estilo no se aplica | Gana otra regla: id > class > etiqueta, y si empatan la de más abajo | Hacer el selector más específico (evitar `!important`) |

---

## 5. 🟦 `position` (el que más cae)

| Valor | Qué hace |
|---|---|
| `static` | Normal (por defecto) |
| `relative` | Se queda en su sitio y **sirve de referencia** para sus hijos `absolute` |
| `absolute` | Se coloca respecto al padre con `position` (si no hay, respecto a la página) |
| `fixed` | Pegado a la ventana, no se mueve al hacer scroll |
| `sticky` | Normal hasta llegar a `top`, y entonces se queda pegado |

```
┌── .tarjeta  (position: relative) ──┐
│                        [etiqueta]  │  ← position: absolute; top: 10px; right: 10px;
│  David Martínez                    │
└────────────────────────────────────┘
```

## 6. 🟦 Caja (box model)

```
┌──────────── margin (fuera) ───────────┐
│ ┌──────── border (borde) ──────────┐  │
│ │ ┌───── padding (aire dentro) ──┐ │  │
│ │ │         contenido            │ │  │
│ │ └──────────────────────────────┘ │  │
│ └──────────────────────────────────┘  │
└───────────────────────────────────────┘
ancho total = width + padding·2 + border·2 + margin·2
```

---

## 7. Si el enunciado dice…

| Pide | Usar |
|---|---|
| Menú fijo arriba | `position: sticky; top: 0;` |
| Botón siempre visible | `position: fixed; right: 20px; bottom: 20px;` |
| Submenú desplegable | Código de abajo |
| Tooltip al pasar el ratón | `::after` con `attr()` |
| Tabla con scroll | Contenedor con `height` + `overflow-y: auto` |
| Filas alternas | `tr:nth-child(odd)` |
| Círculo | `border-radius: 50%` con mismo ancho y alto |
| Que se adapte al móvil | `@media (max-width: 600px) { ... }` |

---

## 8. Código para copiar

**Submenú desplegable**
```css
nav li { position: relative; }
.submenu { display: none; position: absolute; left: 0; background: #7A1F3D; }
.submenu li { display: block; }
nav li:hover .submenu { display: block; }
```

**Tooltip con `data-tip`** (HTML: `<span class="precio" data-tip="IVA incluido">`)
```css
.precio { position: relative; }
.precio:hover::after {
  content: attr(data-tip);
  position: absolute; bottom: 100%; right: 0;
  background: #222; color: #fff; padding: 4px 8px; border-radius: 4px;
}
```

**Tabla con scroll y cabecera fija**
```css
.tabla-scroll { height: 200px; overflow-y: auto; }
.tabla-scroll th { position: sticky; top: 0; }
```

**Botón flotante**
```css
.flotante { position: fixed; right: 20px; bottom: 20px; }
```

**Tarjeta con etiqueta en la esquina**
```css
.tarjeta { position: relative; }
.etiqueta { position: absolute; top: 10px; right: 10px; }
```

**Adaptar al móvil**
```css
.pagina { max-width: 900px; width: 100%; margin: 0 auto; }
@media (max-width: 600px) {
  .tarjeta { width: 100%; }
}
```

**Formulario completo**
```html
<form>
  <p><label for="nombre">Nombre</label> <input type="text" id="nombre"></p>
  <p><label for="correo">Correo</label> <input type="email" id="correo"></p>
  <p><label for="msg">Mensaje</label> <textarea id="msg"></textarea></p>
  <button type="submit">Enviar</button>
</form>
```

**Estados de un enlace o campo**
```css
a:hover { background: #E0A526; }
input:focus { border-color: #E0A526; outline: none; }
```

---

## 9. Selectores rápidos

| Selector | Significa |
|---|---|
| `p` | todos los `<p>` |
| `.tarjeta` | los que tienen `class="tarjeta"` |
| `#contacto` | el que tiene `id="contacto"` |
| `nav a` | los `a` que están dentro de `nav` |
| `h2, h3` | los dos tipos |
| `li:nth-child(odd)` | li impares |
| `a:hover` | al pasar el ratón |
| `h2::before` | algo dentro, antes del h2 |

🟨 En GitHub, un código de color como `#7A1F3D` se ve con su cuadradito de color. Sirve para recordar cuál es cuál.

---

## 10. Mini checklist final (antes de entregar)

- [ ] ¿Se ve el CSS? (el `<link>` está bien)
- [ ] ¿Se ven las imágenes? (rutas)
- [ ] ¿Salen bien las tildes? (charset)
- [ ] ¿Funcionan los enlaces del menú? (ids)
- [ ] ¿Todas las etiquetas están cerradas? (validator)
- [ ] ¿Pasa el `:hover` y el menú?
- [ ] ¿Puse mi nombre en el footer?
- [ ] ¿Guardé todo y subí a GitHub?
