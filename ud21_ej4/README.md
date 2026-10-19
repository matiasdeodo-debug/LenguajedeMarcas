# Ejercicio 4: id y atributos

## Parte A: selector de id

primero puse id="corp" en un h1 y en un h2 a propósito y lo pasé por el
validador de W3C. Me salió este error:

Error: Duplicate ID corp.
From line 10, column 3; to line 10, column 16
Warning: The first occurrence of ID corp was here.
From line 9, column 3; to line 9, column 16

lo corregí cambiando el id repetido por una clase (class="corp") en el
HTML y en el CSS cambié #corp por .corp. al volver a validar ya no salió
ningún error

## ¿Por qué se desaconseja usar el selector de id para estilizar?

prque un id solo se puede usar una vez en la página, así que no sirve
para dar estilo a varios elementos a la vez y si lo repites el HTML ya
no es válido, además es muy específico y cuesta pisarlo con otras reglas
las clases se pueden reutilizar y son más cómodas

## Parte B: selectores de atributo

- a[target]: cambia de color solo los enlaces que tienen el atributo
  target (los que se abren en otra pestaña)
- p[class]: pone fondo gris solo a los párrafos que tienen el atributo
  class, y los que no lo tienen se quedan igual