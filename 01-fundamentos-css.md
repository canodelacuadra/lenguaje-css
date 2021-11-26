# Fundamentos del Lenguaje CSS
Sumario:
1. [Qué es CSS](#Qué-es-CSS)
2. [Formas de incluir CSS](#Formas-de-incluir-CSS)
3. [Sintaxis CSS](#Sintaxis-CSS)
4. [Herencia](#Herencia)
5. [Cascada](#Cascada)
6. [Prioridad](#Prioridad)

Una página web es realmente un documento de texto. En dicho documento se escribe código HTML, con el que se que crea el contenido de una web.

 Por otro lado, existe el código CSS, que unido al código HTML permite darle forma, color, posición (y otras características visuales) a una página.

En resumen, se trata de un idioma como podría ser el inglés o el alemán, que los navegadores web como Chrome o Firefox conocen y pueden entender. Nuestro objetivo como diseñadores y programadores web es precisamente ese: aprender el idioma.

Los navegadores entienden los idiomas HTML y CSS
## Qué es CSS
Las siglas CSS (Cascading Style Sheets) significan «Hojas de estilo en cascada» y parten de un concepto simple pero muy potente: aplicar estilos (colores, formas, márgenes, etc...) a uno o varios documentos (generalmente documentos HTML, páginas webs) de forma masiva.

Se le denomina estilos en cascada porque se aplican de arriba a abajo (cascada) (siguiendo un patrón denominado herencia que trataremos más adelante) y en el caso de existir ambigüedad, se siguen una serie de normas para resolverla.(especificidad)

La idea de CSS es la de utilizar el concepto de separación de presentación y contenido. HTML se encarga del contenido y CSS de la presentación.
## Formas de incluir CSS


En principio, tenemos tres formas diferentes de hacerlo, siendo la primera la más común y la última la menos habitual:


* CSS Externo	Etiqueta ````<link>````	El código se escribe en un archivo .css a parte. Método más habitual.
* CSS Interno	Etiqueta ````<style>````	El código se escribe en una etiqueta ````<style>```` en el documento HTML.
* Estilos en línea	Atributo ```` style="..." ````	El código se escribe en un atributo HTML de una etiqueta.

### Enlace a CSS externo (link) 

En la cabecera de nuestro documento HTML, más concretamente en el bloque ````<head></head>````, podemos incluir una etiqueta ``<link>`` con la que establecemos una relación entre el documento actual y el archivo CSS que indicamos en el atributo href:
````html
<link rel="stylesheet" href="index.css" />
````
De esta forma, los navegadores sabrán que deben aplicar los estilos que se encuentren en el archivo index.css. Se aconseja escribir esta línea lo antes posible (sobre todo, antes de los scripts), obligando así al navegador a aplicar los estilos cuanto antes y eliminar la falsa percepción visual de que la página está en blanco y no ha sido cargada por completo.

Esta es la manera recomendada de utilizar estilos CSS en nuestros documentos.

El atributo type="text/css" no es necesario en HTML5. Muchas veces se indica para mantener retrocompatibilidad con navegadores muy antiguos, pero en la actualidad se puede omitir.

### Incluir CSS en el HTML (style) 
Otra de las formas habituales que existen para incluir estilos CSS en nuestra página es la de añadirlos directamente en el documento HTML, a través de una etiqueta ``<style>`` que contendrá el código CSS:
````html
<!DOCTYPE html>
<html>
  <head>
    <title>Título de la página</title>
    <style>
      div {
        background: hotpink;
        color: white;
      }
    </style>
  </head>
  ...
</html>
````
Este sistema puede servirnos en ciertos casos particulares, pero hay que darle prioridad al método anterior (CSS externo), ya que incluyendo el código CSS en el interior del archivo HTML arruinamos la posibilidad de tener el código CSS en un documento aparte, pudiendo reutilizarlo y enlazarlo desde otros documentos HTML mediante la etiqueta ````<link>````.

Aunque no es obligatorio, es muy común que las etiquetas ````<style>```` se encuentren en la cabecera ````<head>```` del documento HTML, ya que antiguamente era la única forma de hacerlo.

### Estilos en línea (atributo style) 
Por último, la tercera forma de aplicar estilos en un documento HTML es hacerlo directamente, a través del atributo style de la propia etiqueta donde queramos aplicar el estilo, colocando ahí las propiedades CSS:
````html
<p>¡Hola <span style="color:red">amigo lector</span>!</p>
````
De la misma forma que en el método anterior, con la etiqueta ````<style>````, se recomienda no utilizar este método salvo en casos muy específicos y justificados, ya que los estilos se asocian a la etiqueta HTML en cuestión y no pueden reutilizarse.

Es una opción que puede venir bien en ciertos casos, pero se considera una mala práctica por muchos diseñadores cuando la sobreutilizas (sin una razón de peso) pudiendo utilizar el primer método.
## Sintaxis CSS
Al igual que los documentos HTML, los documentos CSS son archivos de texto donde se escribe una serie de órdenes y el cliente (navegador) las interpreta y aplica a los documentos HTML asociados.

La estructura CSS se basa en **reglas** que tienen el siguiente formato:



* Selector: El selector más simple es el elemento HTML que vamos a seleccionar del documento para aplicarle un estilo concreto. Por ejemplo, con ````p```` seleccionaríamos todas las etiquetas ````<p>```` del HTML.

* Propiedad: La propiedad es una de las diferentes características que brinda el lenguaje CSS y que aplicaremos al selector para darle estilo.

* Valor: Cada propiedad CSS tiene una serie de valores concretos a que se le pueden asignar, con los que tendrá uno u otro comportamiento.

* Regla CSS: Con todo esto le iremos indicamos al navegador que, para cada etiqueta (selector especificado) debe aplicar las reglas (propiedad y valor) indicadas.

Vamos a verlo con un ejemplo para afianzar conceptos. Tenemos el siguiente código HTML:
````html
<!DOCTYPE html>
<html>
  <head>
    <title>Título de página</title>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <div id="first">
      <p>Párrafo</p>
    </div>
    <div id="second">
      <span>Capa</span>
    </div>
  </body>
</html>
````
Además, por otro lado, en el archivo index.css indicado en la etiqueta ````<link>```` tenemos el siguiente código CSS que vemos a continuación:
````css
p {
  color: red; /* Color de texto */
}
````
En este caso, estamos seleccionando todas las etiquetas ````<p>```` del documento HTML (en este ejemplo es una sola, pero si existieran más se aplicaría a todas), y les aplicaremos el estilo indicado: color de texto rojo.

> Ojo: Se pueden incluir comentarios entre los caracteres /* y */, los cuales serán ignorados por el navegador. Estos suelen servir para añadir notas o aclaraciones dirigidas a humanos.

Sin embargo, esto es sólo un ejemplo muy sencillo. Se pueden aplicar muchas más reglas (no sólo una, como el color del ejemplo), consiguiendo así un conjunto de estilos para la etiqueta indicada en el selector.

Cada una de estas reglas se terminará con el carácter punto y coma (;), seguido de la siguiente regla. El último punto y coma es opcional y se puede omitir si se desea.

### Legiblilidad

Sin embargo, el código CSS se va haciendo más grande a medida que escribimos, por lo que colocar las reglas una detrás de otra sería muy poco legible. Por esa misma razón, se suele indentar el código. Esto no es más que utilizar una determinada estructura visual (utilizando saltos de línea, es decir, ENTER) de modo que en cada línea sólo haya una regla como máximo.

Esto se considera una buena práctica, indispensable a la larga, que nos facilitará la lectura, escritura y comprensión del código rápidamente:
````css
p {
  color: red; /* Color de texto */
  background-color: white;/* Color de fondo */
}
````

Como puedes ver, esto mejora sustancialmente la legibilidad del código y se considera una convención que debe utilizarse para ayudar a entender más rápidamente el código ajeno (o incluso el nuestro).

## Herencia y cascada
Hay ciertos detalles que hay que tener claros antes de empezar a profundizar en CSS. El concepto de herencia y el de cascada (que veremos más adelante) son dos de las características de CSS más infravaloradas y que más problemas suelen producir, ya que sin lugar a dudas son los que menos se conocen y los que mayor frustración acarrean porque se utilizan indebidamente.

### Concepto de herencia 
En primer lugar, debemos saber que algunas propiedades CSS se heredan desde los elementos padres a los elementos hijos, modificando el valor que tienen por defecto:
````css
body {
  color: green;    /* Color de texto */
}
````
En el ejemplo anterior, aplicamos a la etiqueta HTML ``<body>`` el color de texto verde. En principio, esta propiedad aplicará dicho color a los textos que estén dentro de dicha etiqueta ``<body>``.

Sin embargo, si tenemos más etiquetas dentro, como por ejemplo una etiqueta ``<div>`` con texto en su interior, si no tenemos aplicada una propiedad color a dicho elemento, veremos que también aparece en color verde. Esto ocurre porque la propiedad color es una de las propiedades CSS que, en el caso de no tener valor específico, hereda el valor de su elemento padre.

Ojo, porque esto no ocurre si lo hacemos con otras propiedades CSS, como por ejemplo, con los bordes de un elemento HTML:
````css
body {
  border-width: 2px;
  border-style: solid;
  border-color: red;
}
````
Si esta propiedad aplicara herencia, todos los elementos HTML situados en el interior de ``<body>`` tendrían un borde rojo, comportamiento que no suele ser el deseado. Por esa razón, la herencia no ocurre con todas las propiedades CSS, sino sólo con algunas propiedades como color o font, donde si suele ser deseable.

### Valores especiales de herencia 
Además de los valores habituales de cada propiedad CSS, también podemos aplicar ciertos valores especiales que son comunes a todas las propiedades existentes. Con estos valores modificamos el comportamiento de la herencia en dicha propiedad:


* inherit	Hereda el valor que tiene la misma propiedad CSS en su elemento padre.
* initial	Establece el valor inicial que tenía la propiedad CSS inicialmente.
* unset	Combinación de las dos anteriores: Hereda el valor del padre, y en caso de no existir, su valor inicial.
  
Veamos, por ejemplo, el siguiente ejemplo para forzar la herencia en una propiedad que no la aplica por defecto:
````css
body {
  border-width: 2px;
  border-style: solid;
  border-color: red;
}

div {
  border: inherit;
}
````
Si tenemos un elemento ````<div>```` dentro del ````<body>````, el primero heredará los estilos del elemento ````<body>````, ya que le hemos especificado el valor inherit en la propiedad border.

### Cascada
Otro de los conceptos principales más importantes de CSS es el concepto denominado cascada. De hecho, la cascada es la que le da sentido a la **C** inicial en el nombre de CSS.

En algunos casos, el concepto de cascada es demasiado avanzado como para verlo en un tema de introducción, por lo que se debe conocer bien el tema de selectores CSS y dominar algo de propiedades CSS para comprenderlo totalmente. Si no es el caso, se aconseja que se posponga para una lectura posterior.

Supongamos que nos encontramos ante el siguiente escenario, donde aplicamos unos estilos CSS a exactamente el mismo selector (div) y donde coincide la propiedad CSS color con diferente valor en cada bloque:
````html
<div>Texto del elemento</div>

<style>
div {
  color: red;
  padding: 8px
}

div {
  color: blue;
  background-color: grey
}
</style>
````
En este caso, ¿cuál de las dos reglas prevalece, si tenemos en cuenta que se refieren al mismo elemento y están al mismo nivel? La respuesta es muy fácil: Prevalece siempre **la última regla definida**, la cuál mezcla y sobreescribe las propiedades anteriores.

En el caso anterior, el resultado final (valor computado) sería el siguiente:
````css
div {
  color: blue; /* Se sobreescribe la última */
  padding: 8px;
  background-color: grey;
}
````
Sin embargo, puede ocurrir que en determinados casos no esté tan claro cuál es el estilo que debería sobreescribir a los anteriores. Ahí es cuando entra en juego el concepto de cascada en CSS, que es el que se encarga de eliminar la ambigüedad y determinar el que tiene **prioridad**.

Supongamos el siguiente caso, donde tenemos un mismo elemento ``<div>`` con un id y una clase:
````
<div id="nombre" class="clase">Texto del elemento</div>

<style>
div { color: red; }
#nombre { color: blue; }
.clase { color: green; }
</style>
````

Tenemos un elemento HTML ````<div id="nombre" class="clase">```` que encaja con los tres bloques del ejemplo anterior. ¿Cómo sabe CSS que estilo aplicar? ¿Cuál tiene prioridad sobre los demás? Aquí es donde entra en acción el concepto de prioridad en CSS.

## Prioridad CSS 
El navegador, para saber que bloque de estilos tiene prioridad sobre los demás, analiza (por orden) tres conceptos clave del código CSS: su importancia, su especificidad y su orden. Veamos en que se basa cada uno de ellos.

### Importancia 
La importancia de un código CSS se determina dependiendo de las hojas de estilo donde está colocado. Generalmente, no necesitaremos preocuparnos de este factor, pero siempre es una buena idea conocer como funciona. Existen varios tipos de hojas de estilo, de menor a mayor importancia:


* Agente de usuario	Son los estilos CSS que aplica el navegador por defecto.	Navegador
* CSS de usuario	Son los estilos CSS que añade el usuario, por razones de personalización.	Usuario
* CSS de autor	Son los estilos CSS que coloca el autor de la página.	Desarrollador

### !important
Aunque no es recomendable utilizarlo frecuentemente (puede convertirse en una mala práctica), se puede añadir al final de cada regla el texto !important, consiguiendo que la regla en cuestión tenga prioridad sobre las demás, independientemente del nivel o la altura a la que estén:
````html
<div>Texto del elemento</div>

<style>
div {
  color: red !important;
  padding: 8px
}

div {
  color: blue;
  background-color: grey
}
</style>
````
El resultado final (computado) de este código CSS sería:
````css
div {
  color: red;
  padding: 8px;
  background-color: grey
}
````

> Nota: En el caso de que una misma propiedad del CSS de usuario y una propiedad del CSS de autor tuvieran !important, como caso excepcional tendría prioridad la del CSS de usuario sobre la del CSS de autor.

### Especificidad 
En segundo caso, y si la importancia no elimina la ambigüedad, se pasa a determinar la especificidad de los selectores CSS, que es uno de los criterios más importantes de la cascada de CSS (y también más desconocido).

Para determinar la especificidad de un selector, se sigue un cálculo matemático basado en 4 componentes: A, B, C, D:

* Componente A	Estilos aplicados mediante un atributo style.
* Componente B	Número de veces que aparece un id en el selector.
* Componente C	Número de veces que aparece una clase , pseudoclase o atributo en el selector.
* Componente D	Número de veces que aparece un elemento o un pseudoelementos en el selector.

Para saber si un bloque de CSS es más específico que otro (y por lo tanto, tiene mayor prioridad) sólo hay que calcular sus componentes. Se ordenan teniendo en cuenta los valores de cada componente, de izquierda a derecha. Veamos algunos ejemplos:
````
div { ... }                       /* Especificidad: 0,0,0,1 */
div div { ... }                   /* Especificidad: 0,0,0,2 */
#pagina div { ... }               /* Especificidad: 0,1,0,1 */
#pagina div:hover { ... }         /* Especificidad: 0,1,1,1 */
#pagina div:hover a { ... }       /* Especificidad: 0,1,1,2 */
#pagina .sel:hover>a { ... }      /* Especificidad: 0,1,2,1 */
````
En keegan.st tienes una excelente calculadora de especificidad CSS donde podrás calcular la especificidad de un selector CSS rápida y cómodamente.

### Orden 
En CSS, es posible crear múltiples reglas CSS para definir un mismo concepto. En este caso, la que prevalece ante todas las demás depende de ciertos factores, como es la «altura» a la que está colocada la regla:

1. El CSS en linea en un elemento HTML es el que tiene mayor precedencia, por lo que siempre será el que tenga prioridad sobre otras reglas CSS. Recuerda que son los estilos incluidos en una etiqueta HTML a través del atributo style.

2. En segundo lugar, el CSS interno definido a través de bloques ``<style>`` en el propio documento HTML será el siguiente a tener en cuenta en orden de prioridad.

Por último, los documentos CSS externos son la tercera opción de prioridad a la hora de tomar en cuenta las reglas CSS. Son aquellos que se relacionan en un documento HTML a través de la etiqueta ``<link>``.

Teniendo esto en cuenta, hay que recordar que las propiedades que prevalecerán serán las que estén en último lugar, siempre respetando la prioridad de la lista anterior.







