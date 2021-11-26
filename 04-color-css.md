# Colores en css
Uno de los primeros cambios de estilo que podemos pensar realizar en un documento HTML es hacer variaciones en los colores de primer plano (texto) y de fondo. Esto es posible con las primeras dos propiedades que veremos a continuación:

* color		Cambia el color del texto que está en el interior de un elemento.
* background-color		Cambia el color de fondo de un elemento.
La propiedad color establece el color del texto, mientras que la propiedad background-color establece el color de fondo del elemento.
## Formas alternativas del color
Todas las propiedades CSS donde existen valores , establecen la posibilidad de indicar 4 formas alternativas (con algunos derivados) para especificar el color deseado:


1. Palabra clave predefinida	[palabra clave]	red
2. Esquema RGB	rgb(rojo, verde, azul)	rgb(255, 0, 0)
3. Esquema RGB con canal alfa	rgba(rojo, verde, azul, alfa)	rgba(255, 0, 0, 0.25)
4. Esquema RGB hexadecimal	#RRGGBB	#ff0000
5. Esquema RGB hexadecimal con canal alfa	#RGBBBAA	#ff000040
6. Esquema HSL	hsl(color, saturación, brillo)	hsl(0, 100%, 100%)
6. Esquema HSL con canal alfa	hsla(color, saturación, brillo, alfa)	hsla(0, 100%, 100%, 0.25)
 
A continuación iremos explicando cada uno de estos formatos para entender como se especifican los colores en CSS y utilizar el método que más se adapte a nuestras necesidades.

> Si lo que buscamos es un sistema para extraer colores (eye dropper) de una página web, podemos utilizar la extensión para Chrome de ColorZilla o el propio Chrome Developer Tools, que integra dicha funcionalidad.

##Palabras clave de color 
El primer caso (y más limitado) permite establecer el color utilizando palabras reservadas de colores, como red, blue, orange, white, navy, yellow u otras. Existen más de [140 palabras clave para indicar colores](https://www.w3schools.com/colors/colors_names.asp)

Además, existen algunos valores especiales que puedes utilizar cuando quieras especificar un color, como colores transparentes o el color actual del texto, muy útil para SVG, por ejemplo:


* transparent	Establece un color completamente transparente (valor por defecto de background-color)
* currentColor	Establece el mismo color que se está utilizando para el texto (CSS3 y SVG)
Veamos algunos ejemplos de palabras clave de color:
````
div {
  background-color: blue;
  background-color: transparent;
  background-color: lightpink;
  background-color: rebeccapurple;  /* En honor a Rebeca, la hija de Eric Meyer */
}
````
## Formato RGB 
Uno de los métodos más conocidos por los diseñadores gráficos es utilizar el formato RGB. Las siglas RGB significan rojo, verde y azul, por lo que cada cifra (del 0 al 255) representa la intensidad de cada componente de color. Como se puede ver en la siguiente imagen, si utilizamos una cantidad (0, 0, 0) de cada canal, obtenemos el color negro. En cambio, si utilizamos una cantidad (255, 0, 0), obtendremos el color rojo.



De esta forma, mezclando las cantidades de cada canal, se puede obtener prácticamente cualquier color. Existen muchos esquemas de colores, pero en diseño web nos interesa particularmente el esquema RGB (junto al HSL).


La mayoría de los editores tienen los denominados ColorPicker, que no son más que un sistema cómodo y rápido para elegir un color a base de clics por una paleta o circulo visual. También podemos hacerlo directamente en buscadores como Duck Duck Go o Google.

Veamos algunos ejemplos de colores en formato RGB:
````css
div {
  background-color: rgb(125, 80, 10);       /* Old notation */
  background-color: rgb(125 80 10);         /* New notation */
}
````
## ormato hexadecimal 
El formato hexadecimal es el más utilizado por los desarrolladores web, aunque en principio puede parecer algo extraño y complicado, sobre todo si no has oído hablar nunca del sistema hexadecimal (sistema en base 16 en lugar del que utilizamos normalmente, en base 10).

Cada par de letras simboliza el valor del RGB en el sistema de numeración hexadecimal, así pues, el color #FF0000, o sea HEX(FF,00,00), es equivalente al RGB(255,0,0), que es también equivalente al HSL(0, 100%, 100%). Veamos algunos ejemplos para clarificarlo:

* #FF0000	#F00	255,0,0	red (rojo)
* #000000	#000	0,0,0	black (negro)
* #00FFFF	#0FF	0, 255, 255	cyan (azul claro)
* #9370DB	#97D	147,112,219	mediumpurple (lila)

HailPixel nos proporciona una manera muy sencilla y rápida de seleccionar tonalidades de color en formato hexadecimal con sólo mover el ratón. Por otro lado, en ColorSpire puedes seleccionar el color deseado y observar como varían tanto los valores hexadecimales como los valores RGB o HSL (ver a continuación).

> Como se puede ver en la segunda columna, para ahorrar espacio puedes utilizar el formato hexadecimal abreviado, especificando sólo las primeras tres cifras de cada par. Por ejemplo, #9933AA como #93A. El color abreviado sólo será fiel cuando los pares de cifras sean idénticos (o al menos, aproximados).

Veamos algunos ejemplos del formato hexadecimal (RGB abreviado):
````
div {
  background-color: #512592;
  background-color: #000000;    /* Compactable a #000 */
  background-color: #451;       /* Equivalente a #445511; */
}
````
## Formato HSL 
Las siglas HSL significan color (o matiz), saturación y brillo. La primera cifra selecciona el matiz de color (una cifra de 0 a 360 grados), seleccionando el color del círculo exterior de la imagen. Por su parte, las dos siguientes, son el porcentaje de saturación y el brillo del color, respectivamente (ambos, porcentajes de 0% a 100%).


````
div {
  background-color: hsl(120deg, 25%, 75%);      /* Old notation */
  background-color: hsl(120deg 25% 75%);        /* New notation */
}
````
## Canales Alfa 
Es posible que deseemos indicar un color que tenga cierto grado de transparencia, y de esta forma, refleje el contenido, color o imágenes que se encuentren detrás. Hasta ahora solo conocemos la palabra clave transparent, que es un color de transparencia total (totalmente transparente).

Sin embargo, existe la posibilidad de utilizar los denominados canales alfa, que permiten establecer una transparencia parcial en determinados colores. Estos se pueden establecer en cualquier formato, salvo en los colores con palabras clave. Vamos a ver como hacerlo en cada caso:

Formato RGB: En lugar de rgb() indicamos rgba() para establecer que usaremos un canal alfa. Posteriormente, en lugar de establecer 3 parámetros (rojo, verde, azul), añadiremos uno más, que será el canal alfa. Dicho canal alfa será un valor (del 0 al 1 con decimales) o un porcentaje (del 0% al 100%).

Formato HSL: Prácticamente idéntico al anterior. En lugar de hsl() indicamos hsla(). Añadimos un nuevo valor como canal alfa (valor o porcentaje).

Formato Hexadecimal: Es posible indicar (al final) un par adicional que indique el grado de transparencia. Por ejemplo, el color #FF0000 reescrito como #FF000077 se trataría de dicho color, con un grado de transparencia casi del 50% (00 es 0%, 80 es 50%, FF es 100%).

Veamos algunos ejemplos de cada caso:
````
div {
  background-color: rgba(0, 0, 0, 0.5);             /* Old notation */
  background-color: rgba(0 0 0 / 50%);              /* New notation */
  background-color: hsla(180deg, 50%, 25%, 0.75);   /* Old notation */
  background-color: hsla(180deg 50% 25% / 75%);     /* New notation */
  background-color: #aa44ba80;
}

````

>  Una herramienta genial para seleccionar varios colores en nuestros proyectos es Adobe Color CC. Nos permite escoger entre colores análogos, monocromáticos, tríadas, colores complementarios, compuestos o tonos similares. Muy visual e intuitiva. Otra herramienta, más simple pero muy práctica es HSL Picker, donde puedes elegir el color deseado utilizando el formato de colores HSL y pudiendo seleccionar incluso los canales alfa.