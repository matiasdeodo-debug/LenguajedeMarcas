<!DOCTYPE html>
<!-- Le dice al navegador que esto es un documento HTML5 -->
<html lang="es">
<!-- html es la etiqueta que lo envuelve todo; lang="es" = la página está en español -->
<head>
    <!-- head = información de la página que NO se ve -->
    <meta charset="UTF-8">
    <!-- charset UTF-8: para que se vean bien las tildes y la ñ -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- viewport: hace que la página se adapte al ancho del móvil -->
    <title>Club de Senderismo Monte Verde</title>
    <!-- title: el texto que sale en la pestaña del navegador -->
    <link rel="stylesheet" href="estilos.css">
    <!-- link: conecta el CSS. El nombre tiene que ser IGUAL que el archivo -->
</head>
<body>
    <!-- body = todo lo que se ve en la página -->

    <div class="contenedor">
        <!-- div = caja sin significado, sirve para agrupar.
             class="contenedor" = etiqueta para darle estilo (960px y centrado).
             Se cierra DESPUÉS de las secciones y ANTES del footer -->

        <header id="arriba">
            <!-- header = cabecera. id="arriba" = nombre único: es el destino del botón "Subir" -->
            <h1>Club de Senderismo Monte Verde</h1>
            <!-- h1 = título principal (solo uno por página) -->
            <p>Rutas, amistad y naturaleza</p>
            <!-- p = párrafo de texto -->
            <div class="sello">Nueva temporada</div>
            <!-- sello = el círculo naranja; con CSS se coloca en la esquina -->
        </header>

        <nav>
            <!-- nav = zona del menú de navegación -->
            <ul>
                <!-- ul = lista (sin orden). Dentro solo van li -->
                <li><a href="#inicio">Inicio</a></li>
                <!-- li = un elemento de la lista; a = enlace.
                     href="#inicio" = lleva al elemento con id="inicio" de esta misma página -->
                <li><a href="#rutas">Rutas</a></li>
                <li><a href="#galeria">Galería</a></li>
                <li><a href="#opiniones">Opiniones</a></li>
            </ul>
        </nav>

        <section id="inicio">
            <!-- section = bloque de contenido con un tema. El id coincide con el href del menú -->
            <h2>Inicio</h2>
            <!-- h2 = título de la sección (un escalón por debajo del h1) -->
            <p>Explora la naturaleza con nosotros y descubre rutas increíbles.</p>
        </section>

        <section id="rutas">
            <h2>Nuestras Rutas</h2>
            <article class="tarjeta">
                <!-- article = una tarjeta independiente. class="tarjeta" para darle estilo a las 3 -->
                <div class="foto"></div>
                <!-- foto = caja vacía; con CSS tendrá altura y color y hará de foto -->
                <span class="nivel">Fácil</span>
                <!-- span = trozo de texto en línea. nivel = la pastilla naranja sobre la foto -->
                <h3>Ruta del Bosque Encantado</h3>
                <!-- h3 = título de la tarjeta (un escalón por debajo del h2) -->
                <p>Disfruta de un paseo relajante por senderos rodeados de árboles milenarios y fauna local.</p>
            </article>
            <article class="tarjeta">
                <div class="foto"></div>
                <span class="nivel">Media</span>
                <h3>Ruta del Lago Escondido</h3>
                <p>Una caminata que te llevará a un lago cristalino escondido entre montañas.</p>
            </article>
            <article class="tarjeta">
                <div class="foto"></div>
                <span class="nivel">Difícil</span>
                <h3>Ruta del Pico del Águila</h3>
                <p>Para los más aventureros, esta ruta ofrece vistas panorámicas impresionantes desde la cima.</p>
            </article>
        </section>

        <section id="galeria">
            <h2>Galería de Fotos</h2>
            <div class="polaroid"><span>Amanecer en la Ruta del Lago Escondido</span></div>
            <!-- polaroid = la foto (un div de color). El span de dentro es el pie de foto,
                 que con CSS se pega al borde de abajo -->
            <div class="polaroid"><span>Sendero del Bosque Encantado</span></div>
            <div class="polaroid"><span>Vista desde el Pico del Águila</span></div>
        </section>

        <section id="opiniones">
            <h2>Opiniones de Nuestros Miembros</h2>
            <div class="caja">
                <!-- caja = contenedor de las 6 opiniones. Es la que tendrá 170px de alto y scroll.
                     Se abre aquí y se cierra después del último article -->
                <article><h3>Ana G.</h3><p>"Una experiencia inolvidable, la naturaleza en su máxima expresión."</p></article>
                <article><h3>Javier M.</h3><p>"Las rutas son variadas y bien señalizadas. ¡Recomendado!"</p></article>
                <article><h3>Lucía R.</h3><p>"Me encanta la comunidad y la camaradería que se respira en cada salida."</p></article>
                <article><h3>Carlos T.</h3><p>"Cada ruta es una aventura diferente, siempre hay algo nuevo que descubrir."</p></article>
                <article><h3>María L.</h3><p>"Los guías son muy profesionales y hacen que la experiencia sea segura y divertida."</p></article>
                <article><h3>Pedro S.</h3><p>"La organización del club es excelente, siempre atentos a los detalles."</p></article>
            </div>
        </section>

    </div>
    <!-- Aquí se cierra el contenedor. El footer queda FUERA, como pide el enunciado -->

    <footer>
        <!-- footer = pie de página -->
        <p>© 2026. Matías Nicolás González</p>
        <a href="#arriba" class="subir">↑ Subir</a>
        <!-- href="#arriba" = vuelve al header con id="arriba".
             class="subir" = con CSS será el botón fijo abajo a la derecha -->
    </footer>
</body>
</html>




CSS:

/* ===== PÁGINA ===== */
body {
    background-color: #e9efe9;      /* fondo de toda la página: verde muy claro */
    font-family: Arial, sans-serif; /* letra de toda la web (sans-serif = plan B) */
    color: #222;                    /* color del texto: negro suave */
    margin: 0;                      /* quita el borde blanco que pone el navegador */
}

.contenedor {                       /* el punto = es una CLASE */
    width: 960px;                   /* ancho fijo que pide el enunciado */
    margin: 0 auto;                 /* 0 arriba/abajo y auto en los lados: queda CENTRADO */
    background-color: white;        /* fondo blanco sobre el verde claro */
}

/* ===== CABECERA + EFECTO 2: SELLO (relative + absolute) ===== */
header {
    position: relative;             /* NO lo mueve: lo convierte en el punto de referencia del sello */
    background-color: #2f5d46;      /* verde oscuro */
    color: white;                   /* texto blanco */
    padding: 30px;                  /* espacio por dentro, entre el borde y el texto */
}

.sello {
    position: absolute;             /* sale del flujo y se coloca respecto al padre con position */
    top: 16px;                      /* a 16px del borde de arriba del HEADER */
    right: 16px;                    /* y a 16px del borde derecho del HEADER */
    width: 84px;                    /* tamaño que pide el enunciado */
    height: 84px;
    box-sizing: border-box;         /* el padding NO agranda la caja */
    padding-top: 28px;              /* baja el texto para centrarlo */
    border-radius: 50%;             /* 50% = redondea del todo: círculo */
    background-color: #f08a24;      /* naranja */
    color: white;
    text-align: center;             /* texto centrado */
    font-size: 12px;
    line-height: 14px;              /* altura de cada línea de texto */
    font-weight: bold;              /* negrita */
}

/* ===== MENÚ + EFECTO 1: PEGADO ARRIBA (sticky) ===== */
nav {
    position: sticky;               /* normal hasta que el scroll lo lleva al borde; luego se pega */
    top: 0;                         /* se pega a 0px del borde de arriba. SIN top no funciona */
    z-index: 10;                    /* capa: número alto = queda POR ENCIMA del contenido */
    background-color: #2f5d46;
}
nav ul {
    list-style-type: none;          /* quita los puntitos de la lista */
    margin: 0;                      /* quita el hueco que el navegador pone por defecto */
    padding: 0;
}
nav li {
    display: inline-block;          /* los li se ponen EN FILA en vez de uno debajo de otro */
}
nav a {
    display: block;                 /* el enlace ocupa toda su caja, así el padding funciona bien */
    color: white;
    text-decoration: none;          /* quita el subrayado del enlace */
    padding: 14px 20px;             /* espacio por dentro: 14px arriba/abajo, 20px a los lados */
}
nav a:hover {                       /* :hover = cuando el ratón está encima */
    color: #f08a24;                 /* se pone naranja */
}

/* ===== SECCIONES ===== */
section {
    padding: 20px 30px;             /* separa el contenido del borde */
}
h2 {
    color: #2f5d46;                 /* títulos en verde oscuro */
}

/* ===== TARJETAS DE RUTAS ===== */
.tarjeta {
    position: relative;             /* es el padre de la pastilla de nivel (efecto 3) */
    overflow: hidden;               /* lo que sobresalga de la tarjeta se RECORTA */
    display: inline-block;          /* las 3 tarjetas EN FILA, pero siendo cajas con ancho */
    width: 270px;                   /* ancho que pide el enunciado */
    vertical-align: top;            /* alineadas por arriba */
    margin-right: 15px;             /* hueco entre tarjetas */
    background-color: white;
    border: 1px solid #ccc;         /* borde gris finito */
}
.tarjeta h3, .tarjeta p {           /* la coma = "los dos" */
    margin: 8px 12px;               /* para que el texto no toque el borde */
}

/* EFECTO 4: TARJETA CENTRAL (relative con top negativo) */
.tarjeta:nth-child(3) {             /* la central: hijo nº3 (el 1 es el h2) */
    position: relative;             /* se mueve desde su sitio y deja su hueco: no empuja a las vecinas */
    top: -12px;                     /* sube 12px */
    box-shadow: 0 6px 14px rgba(0, 0, 0, 0.3);  /* sombra: 0 lado, 6px abajo, 14px difuminado, negro al 30% */
}

.foto {
    height: 130px;                  /* sin altura el div vacío mediría 0 y no se vería */
}
.tarjeta:nth-child(2) .foto { background-color: #8fb996; }  /* "la foto dentro de la tarjeta 2" */
.tarjeta:nth-child(3) .foto { background-color: #a7c5d9; }
.tarjeta:nth-child(4) .foto { background-color: #e5c07b; }

/* EFECTO 3: ETIQUETA DE NIVEL (relative + absolute + overflow) */
.nivel {
    position: absolute;             /* se coloca respecto a la TARJETA (que tiene relative) */
    top: 10px;                      /* a 10px de la esquina superior... */
    right: 10px;                    /* ...derecha de cada tarjeta */
    background-color: #f08a24;
    color: white;
    padding: 4px 10px;
    border-radius: 20px;            /* esquinas redondas: forma de pastilla */
    font-size: 12px;
}

/* ===== EFECTO 5: GALERÍA DE POLAROIDS (relative + absolute + z-index) ===== */
.polaroid {
    position: relative;             /* referencia del pie de foto Y permite usar z-index */
    display: inline-block;          /* en fila */
    vertical-align: top;
    width: 280px;                   /* tamaño que pide el enunciado */
    height: 210px;
    border: 6px solid white;        /* marco blanco de la polaroid */
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.35);  /* sombra, para ver el borde blanco sobre el blanco */
}
.polaroid:nth-child(2) { background-color: #8fb996; }                         /* la 1ª polaroid (hijo 2) */
.polaroid:nth-child(3) { background-color: #a7c5d9; margin-left: -40px; z-index: 2; } /* margen NEGATIVO = se mete encima de la anterior; z-index 2 = queda encima de las otras */
.polaroid:nth-child(4) { background-color: #e5c07b; margin-left: -40px; }
.polaroid:hover { z-index: 3; }     /* al pasar el ratón: 3 es mayor que 2, así salta al frente */

.polaroid span {                    /* el pie de foto */
    position: absolute;             /* se coloca respecto a la polaroid */
    bottom: 0;                      /* pegado al borde de abajo */
    left: 0;
    width: 100%;                    /* ocupa todo el ancho de la foto */
    background-color: white;
    text-align: center;
    padding: 6px 0;
    font-size: 13px;
}

/* ===== EFECTO 6: OPINIONES CON SCROLL (overflow) ===== */
.caja {
    height: 170px;                  /* alto fijo: la caja no se agranda */
    overflow: auto;                 /* si el contenido no cabe, aparece la barra de scroll */
}

/* ===== FOOTER + EFECTO 7: BOTÓN SUBIR (fixed) ===== */
footer {
    text-align: center;
    padding: 20px;
}
.subir {
    position: fixed;                /* se coloca respecto a la VENTANA y no se mueve al hacer scroll */
    bottom: 20px;                   /* a 20px del borde de abajo de la ventana */
    right: 20px;                    /* y a 20px del borde derecho */
    background-color: #f08a24;
    color: white;
    padding: 10px 16px;
    text-decoration: none;          /* sin subrayado */
}
