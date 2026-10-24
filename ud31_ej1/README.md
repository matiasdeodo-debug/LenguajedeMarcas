# UD3.1 ejercicio 1 - laboratorio de position

Matias Nicolas Gonzalez, 1 ASIX

- static: le puse left: 50px a c1 y no se mueve, porque static es el valor por defecto y no hace caso a top, left, right ni bottom
- relative: c2 con top: 20px y left: 50px se desplaza pero deja su hueco vacio, los demas cuadros no ocupan ese sitio
- absolute: c3 con top: 0 y right: 0 se va a la esquina de la pagina, al ponerle position: relative al contenedor se va a la esquina del contenedor, porque se coloca respecto al padre posicionado mas cercano, y como sale del flujo ya no ocupa sitio y el texto de abajo sube
- z-index: subi c2 con top: -40px y tapa a c1, para que c1 quede encima le puse z-index: 2 y a c2 z-index: 1, y a c1 le puse position: relative porque el z-index no funciona en static

