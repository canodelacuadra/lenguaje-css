# Representación de datos
## tablas
Las tablas de HTML son un grupo de etiquetas de HTML que sirven para mostrar datos tabulados. En el pasado, se utilizaron de forma errónea para crear un diseño, debido a su facilidad de colocación al ser un esquema rectángular. Afortunadamente, hoy en día ya se ha perdido esa percepción incorrecta, aunque nunca está de más conocer un poco de historia para no repetir los errores del pasado.

Cuando queremos dar estilo a una tabla de HTML, podemos utilizar propiedades genéricas como border, background, color, font-family, padding, margin, entre otras. Combinándolas en los diferentes elementos HTML de tablas, en particular, celdas ``<td>``, encabezados ``<th>``, filas ``<tr>`` y tablas ``<table>``, podemos personalizar mucho el aspecto visual de la misma.

## Propiedades CSS para tablas 
Sin embargo, también existen varias propiedades CSS específicas para alterar o modificar el comportamiento de ciertas características de una tablas HTML. Veamos cuales son esas propiedades específicas para tablas:

* border-collapse	separate | collapse	Aplicado sobre la tabla, elimina el espacio de relleno entre celdas.
* border-spacing	0 | 	Amplia el espacio de relleno entre tabla y celdas.
* caption-side	top | bottom	Mueve el elemento ``<caption>`` del interior de una tabla.
* empty-cells	show | hide	Hace desaparecer visualmente una celda vacía (sin contenido).
* table-layout	auto | fixed	Indica si las celdas deben ajustarse o tener un tamaño fijo.

### La propiedad border-collapse 
permite especificar si los bordes de una tabla y sus celdas deben estar unidos (collapse) o separados (separate). En el segundo caso, se puede también aplicar la propiedad border-spacing, que especifica el tamaño que medirán los espacios exteriores entre celdas.

### La propiedad caption-side 
permite especificar donde se colocará el título de la tabla (en el caso de haber utilizado el elemento HTML ``<caption>``): al principio de la tabla (top) o al final (bottom).

### La propiedad empty-cells 
establece si mostrar (show) o no (hide) las celdas vacías, haciéndolas desaparecer en el último caso.

### la propiedad table-layout 
permite especificar si el navegador debe adaptar el tamaño de las celdas automáticamente (auto) o establecer un tamaño fijo (fixed).

## listas
De la misma forma que las tablas, las listas también poseen sus propias propiedades específicas para alterar el estilo o características de listas HTML, tanto listas ordenadas ``<ol>`` como listas sin orden ``<ul>``.

* list-style-image	none | url(image.png)	Especifica una imagen para usar como «punto» o viñeta de ítem.
* list-style-position	inside | outside
* list-style-type none|circle|square|disc	

Establece o elimina indentación de ítems sobre la lista.

### list-style-image
 permite indicar la URL de una imagen para utilizar de icono o viñeta en cada ítem de la lista. Con el valor none eliminamos el uso de cualquier imagen.

### list-style-position 
permite establece una indentación a todos los ítems de la lista, estableciendolos desplazados a la derecha (inside) o sin desplazar (outside).

### list-style-type 
nos permite indicar que tipo de numeración tendrán las listas (en el caso de no estar utilizando ningun imagen). Se establecen tres grupos. El primero indicado para las listas que no requieren orden, el segundo para las listas numeradas y el tercero para las listas numeradas que queremos especificar con letras (números romanos, letras griegas, etc...).

Veamos cada uno de los valores posibles:

* list-style-type	disc | circle | square | none	Viñetas sin orden
* list-style-type	decimal | decimal-leading-zero | lower-roman | upper-roman	Viñetas numéricas
* list-style-type	lower-alpha | | upper-alpha | lower-greek	Viñetas alfabéticas

El primer grupo, indicado para listas sin orden ``<ul>``:

* disc: Un pequeño circulo relleno.
* circle: Un circulo vacío.
* square: Un cuadrado relleno.
* none: No muestra ninguna marca a la izquierda de los ítems.
  
Si lo que queremos es establecer una lista numerada ``<ol>``, podemos utilizar valores como:

* decimal: Numeración decimal: 1, 2, 3, 4, 5...
decimal-leading-zero: Numeración decimal con ceros: 01, 02, 03, 04, 05...
* lower-roman: Números romanos en minúsculas: i, ii, iii, iv, v...
* upper-roman: Números romanos en mayúsculas: I, II, III, IV, V...
* lower-alpha / lower-latin: Minúsculas: a, b, c, d, e...
* upper-alpha / upper-latin: Mayúsculas: A, B, C, D, E...
* Otras menos utilizadas generalmente, como lower-greek (letras griegas minúsculas), arabic-indic (números árabes), upper-armenian / armenian (letras armenias en mayúsculas), lower-armenian (letras armenias en minúsculas) o georgian (letras georgianas).

Existen otros valores como bengali, cambodian, hebrew, devanagari, gujarati, gurmukhi, kannada, lao, malayalam, mongolian, myanmar, oriya, persian, tamil, telugu. thai, tibetan, hiragana, hiragana-iroha, katakana, katakana-iroha, entre otros.

### Atajo o Propiedades shorthand: Listas 
Es posible utilizar la propiedad de atajo list-style para especificar varias propiedades en una sola. El orden aconsejado es el siguiente:
````css
div {
    /* list-style: <type> <position> <image> */
    list-style: circle inside none;
}
````
