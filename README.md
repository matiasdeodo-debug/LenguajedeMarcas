# Repaso del examen: Librería La Página

Qué falló, por qué falló y cómo se arregla. Todo se resuelve solo con CSS.

## Las 4 ideas que explican casi todo

1. **`position: absolute`** se coloca respecto al ancestro más cercano que tenga `position` (normalmente `relative`). Si no hay ninguno, se va a la página entera.
2. **`position: sticky`** necesita un `top` (o `bottom`, etc.). Sin él no hace nada.
3. **`overflow: hidden`** corta el contenido. Para tener scroll se usa `auto` (o `scroll`).
4. **`content`** en `::before` / `::after` necesita comillas: `content: "★"`.

## Lista de fallos

| # | Qué se veía mal | Causa | Arreglo |
|---|---|---|---|
| 1 | La ★ de los `h2` no aparecía | `content: ★;` sin comillas, así que el CSS es inválido y se ignora | `content: "★";` |
| 2 | El menú no se quedaba arriba al hacer scroll | `position: sticky` sin `top`, y sin `z-index` el contenido lo puede tapar | `nav { position: sticky; top: 0; z-index: 10; }` |
| 3 | Los submenús (Novelas, Cocina, Ciencia) nunca salían | `.submenu` tiene `display: none` y no hay ninguna regla que lo cambie | `nav li:hover > .submenu { display: block; }` |
| 3b | (extra del submenú) Aunque saliera, se colocaría mal | Su `li` padre no tiene `position: relative` y el `li` del submenú es `inline-block` | `nav li { position: relative; }` `.submenu { position: absolute; top: 100%; left: 0; }` `.submenu li { display: block; }` |
| 4 | Los círculos de precio aparecían en cualquier sitio | `.precio` es `absolute` pero `.tarjeta` no tiene `position` | `.tarjeta { position: relative; }` |
| 5 | La 3ª tarjeta caía a otra línea | 284px + borde + márgenes, por 3, es más que los 852px útiles (900 menos el padding de 24px a cada lado) | `box-sizing: border-box; width: 260px;` |
| 6 | La tabla de la agenda no se podía desplazar | `overflow: hidden` | `overflow: auto;` |
| 7 | La cabecera de la tabla no se quedaba fija | `th` sticky sin el contenedor scrolleable (y sin `top: 0` funciona mal, aquí sí lo tiene, pero depende del fallo 6) | Arreglar el 6 |
| 8 | El botón "Contactar" no seguía en pantalla | `.flotante` era `absolute` | `position: fixed;` |
| 9 | El tooltip "IVA incluido" no existía | El HTML tiene `data-tip` pero no hay CSS que lo muestre | Ver abajo |
| 10 | El pie decía "NOMBRE DEL ALUMNO/A" | Faltaba poner tu nombre | Escribirlo (punto fácil) |

### Tooltip con `attr()`

```css
.precio:hover::after {
  content: attr(data-tip);
  position: absolute;
  bottom: 80px;
  right: 0;
  background: #222;
  color: #fff;
  padding: 6px 10px;
  border-radius: 6px;
  font-size: 12px;
  line-height: 1.2;
  white-space: nowrap;
}
```

## CSS completo con los cambios

```css
nav { position: sticky; top: 0; z-index: 10; background: #7A1F3D; }
nav li { display: inline-block; position: relative; }

.submenu { display: none; position: absolute; left: 0; top: 100%;
           background: #7A1F3D; min-width: 160px; padding: 0; z-index: 20; }
.submenu li { display: block; }
nav li:hover > .submenu { display: block; }

h2::before { content: "★"; color: #E0A526; }

.tarjeta { position: relative; box-sizing: border-box; width: 260px; }

.tabla-scroll { height: 200px; overflow: auto; border: 1px solid #ccc; }

.flotante { position: fixed; }
```

## Por qué te dejan usar GitHub y el inspector en el examen

El profesor no me lo ha explicado, así que esto es lo más probable, no una certeza:

- **El inspector (F12) es la herramienta normal de trabajo.** Ningún programador arregla CSS "a ojo". Lo abre, selecciona el elemento y mira qué reglas se aplican, cuáles están tachadas (inválidas o sobreescritas) y qué `position` o `width` tiene. Un examen de "reparar la página" mide si sabes diagnosticar, y eso se hace con el inspector.
- **Lo que se evalúa es que sepas qué buscar.** Con el inspector ves *que* algo falla, pero tienes que saber *por qué* (por ejemplo, que un `absolute` necesita un padre con `position`). Eso no te lo da la herramienta.
- **GitHub** probablemente sirve para tener el código del examen, versionarlo y entregarlo, y es una herramienta que se usa en el trabajo real.

Consejo práctico: en el inspector, las propiedades **tachadas** o con un **triángulo amarillo** te señalan casi siempre el fallo (como `content: ★`).

## Checklist para el examen de mañana

Ante cada elemento que "no se ve bien", pregúntate en este orden:

1. ¿Es `absolute`? Entonces, ¿su padre tiene `position: relative`?
2. ¿Es `sticky`? Entonces, ¿tiene `top: 0`?
3. ¿Debería hacer scroll? Entonces, ¿tiene `overflow: auto`?
4. ¿Hay un `content`? Entonces, ¿tiene comillas?
5. ¿Algo se desborda de su fila? Suma `width` + borde + padding + márgenes y compara con el espacio disponible.
6. ¿Hay `display: none` que debería aparecer al pasar el ratón? Falta la regla con `:hover`.
7. ¿El HTML tiene `data-algo`? Seguramente se espera un `attr()`.
8. ¿Has puesto tu nombre en el pie?

## Examen de práctica

Tienes `practica.html` y `practica.css` (con fallos). Arréglalos solo tocando el CSS. Las soluciones están en `practica-soluciones.md`: **no las mires hasta haber terminado**.
