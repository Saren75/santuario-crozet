# Santuario Crozet

Web de apadrinamiento de la Zona 1 de la Isla Alfred Faure. Proyecto académico
ficticio.

HTML, CSS y JavaScript sin frameworks ni compilación. Funciona igual publicada
en GitHub Pages que abierta con doble clic en `index.html`.

## Estructura

```
index.html        Portada
isla.html         Geografía, clima y fauna
proyecto.html     Las tres zonas y el bucle de financiación
apadrina.html     Rejilla de los ocho pingüinos, con filtros
ficha.html        Plantilla de ficha + formulario + certificado
css/base.css          Variables de diseño, tipografía y estructura
css/componentes.css   Componentes
js/datos.js           Los ocho pingüinos y las cuotas
js/efectos.js         Entradas al hacer scroll, conteo de cifras
js/listado.js         Rejilla y destacados
js/ficha.js           Rellena la ficha según ?id=
js/formulario.js      Validación y certificado
img/                  Fotos
```

## Foto de portada

Opcional. Si dejas una imagen en `img/portada.jpg`, se usa como fondo de la
portada por debajo del degradado. Si no existe, se ve solo el degradado con las
curvas de nivel, que ya funciona por sí solo. Apaisada y de al menos 1600 px de
ancho.

## Los efectos

Los bloques entran al hacer scroll y las cifras cuentan hasta su valor. Todo es
decorativo y está hecho a prueba de fallos: la regla que esconde los bloques
solo se aplica si el JavaScript ha corrido, los valores finales de las cifras
están escritos en el HTML, y si el sistema tiene activado "reducir movimiento"
no se anima nada. Sin JavaScript la web se ve entera, sin animaciones.

## Poner las fotos

Deja los archivos en `img/` con estos nombres exactos. No hay que tocar código:
mientras falten, sale un marcador de posición.

```
img/K-0427.jpg  img/K-0518.jpg  img/K-0634.jpg  img/K-0702.jpg
img/K-0815.jpg  img/K-0931.jpg  img/P-0113.jpg  img/P-0147.jpg
```

Recórtalas en cuadrado (1:1). Con 800×800 px va de sobra; conviene no pasar de
300 KB por archivo.

Las fotos tienen que ser de licencia libre. Wikimedia Commons, categoría
*Aptenodytes patagonicus*, es el mejor sitio. Comprueba la licencia en la página
de cada archivo: CC BY, CC BY-SA o dominio público valen. Apunta autor, título y
licencia de cada una y sustituye "Fotografías: pendientes de atribución" en el
pie de las cinco páginas por las atribuciones reales. CC BY y CC BY-SA obligan
a citar al autor.

## Paleta

Cinco colores, definidos como variables al principio de `css/base.css`. Ninguna
regla escribe un color a mano, así que cambiar la paleta son cinco líneas.

| Color | Hex | Uso |
| --- | --- | --- |
| Navy | `#2F4156` | Texto, titulares, pie, botón principal, Zona 2 |
| Teal | `#567C8D` | Texto secundario, enlaces, detalles, Zona 1 |
| Sky Blue | `#C8D9E6` | Líneas, fondos suaves, trama del mar, Zona 3 |
| Beige | `#F5EFEB` | Fondo de sección cálido, tierra en el mapa |
| White | `#FFFFFF` | Fondo base |

## Cambiar los datos

Todo está en `js/datos.js`: los ocho pingüinos y los tres importes. Nombres,
anillas, colonias e investigadores son inventados; cámbialos a gusto.

Ninguno tiene nombre a propósito: el nombre lo pone el padrino y es el que sale
en el certificado.

## Publicar en GitHub Pages

1. Crea el repositorio en tu cuenta y sube esta carpeta tal cual.
2. Settings → Pages → Source: *Deploy from a branch*, rama `main`, carpeta `/root`.
3. En un par de minutos queda en `https://<usuario>.github.io/<repositorio>/`.

Esa es la dirección que va en el código QR del póster. Si el QR tiene que
apuntar a un pingüino concreto, añade el parámetro:
`https://<usuario>.github.io/<repositorio>/ficha.html?id=K-0427`

## Por qué no se usa fetch() ni módulos ES

El navegador los bloquea cuando la página se abre como archivo local
(`file://`). Manteniendo los datos en `datos.js` y usando etiquetas `<script>`
normales, la web funciona también con doble clic, sin servidor y sin internet.
Es el seguro por si el día de la presentación falla la red.

## Antes de entregar

- [ ] Contrastar las cifras de la portada y de `proyecto.html` con el dossier.
- [ ] Fotos puestas y atribuciones escritas en el pie.
- [ ] Abrirla en el portátil que se va a usar, con doble clic y con el wifi apagado.
- [ ] Consola del navegador sin errores en las cinco páginas.
- [ ] Verla a pantalla completa y desde varios metros.
- [ ] Probar el certificado con Imprimir → Guardar como PDF.
