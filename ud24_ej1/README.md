# UD2.4 ejercicio 1 - portfolio con divs

en este ejercicio hice la pagina del portfolio solo con divs y en la parte A centre la pagina con margin: 0 auto y le puse fondo y borde a cada caja para ver donde empieza cada una, en la parte B probe las tarjetas en block, inline-block y flex, en la parte C probe el span y el display none

al final deje flex en .contenido porque con inline-block quedaba un huequito entre las tarjetas y con flex no, y ademas es mas facil de usar

## Preguntas

1. Diferencia entre margin y padding

el padding es el espacio que hay dentro de la caja, entre el texto y el borde. El margin es el espacio de afuera, entre la caja y las otras cajas

2. Por que la tercera tarjeta saltaba de linea

porque cada tarjeta ocupa mas de 220px. Hay que sumar el padding, el borde y el margin: 220 + 30 + 2 + 20 = 272px. las tres juntas son 816px y la pagina tiene 800px, asi que no entran, lo arregle poniendo width 200px, que da 252 por tarjeta y 756 en total, y asi entran

3. Que propiedades ignoraba el span y por que

ignoraba el width, el height y el margin de arriba y abajo, porque el span es un elemento en linea y se comporta como texto, cuando lo puse en inline-block ya me hizo caso en todo

4. Que hace display none con el espacio

no deja ningun hueco, la tarjeta desaparece y las otras ocupn su lugar
