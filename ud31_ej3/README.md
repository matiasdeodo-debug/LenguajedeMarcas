# UD3.1 ejercicio 3 - tarjeta de producto y caja con scroll

Matias Nicolas Gonzalez, 1 ASIX

parte A:
- la tarjeta necesita position: relative, si no la etiqueta se coloca respecto a la pagina
- con overflow: hidden en la tarjeta la parte de la etiqueta que sobresale se corta, porque hidden esconde todo lo que se sale de la caja
- lo arreglaria quitando el overflow: hidden o poniendo la etiqueta dentro de la tarjeta con top: 0 y right: 0
Parte B:
- visible: el contenido se sale de la caja y se ve por fuera
- hidden: lo que no cabe se corta y no se puede ver
- scroll: siempre salen las barras, aunque no hagan falta
- auto: la barra sale solo si no cabe, es el que dejo
- visibility: hidden esconde la tarjeta pero deja el hueco, display: none la quita del todo y no deja hueco
