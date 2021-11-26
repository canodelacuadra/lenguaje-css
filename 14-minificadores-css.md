Normalmente, cuando el desarrollador escribe código (y no sólo CSS, sino también HTML o Javascript) tiene que mantener un equilibrio entre varios factores clave, entre los que podemos destacar los siguientes:

Funcionamiento: El código debe estar bien escrito para funcionar correctamente. Siempre. Además, se debe cuidar el correcto funcionamiento en diferentes navegadores, diferentes sistemas operativos (incluyendo dispositivos de escritorio, móviles y/o tablets), los cuales suelen/pueden tener algunas diferencias considerables.

Legibilidad: El código debe estar correctamente indentado, facilitando la legibilidad por humanos, favoreciendo la velocidad de modificación e introducción de cambios (mantenibilidad).

Tamaño: Cuanto más texto tenga un archivo CSS, HTML o Javascript (espacios, líneas en blanco, comentarios, código no usado...), más grande será el tamaño final del archivo, por lo que más tiempo tardará en descargarse, y probablemente, en procesarse por el navegador.

Rendimiento: Cuanto más costosas sean las operaciones que vamos a obligar a hacer al navegador, más tardará en procesarse y por lo tanto, más tiempo tardará en pintar y renderizar (dibujar) la página.

¿Qué es la minificación? 
La minificación (en inglés, uglify o minification) es la acción de eliminar carácteres o comentarios en un archivo de código (.html, .css o .js, por ejemplo), ya que su omisión no hace que el código deje de funcionar. El objetivo es reducir su tamaño total, y por lo tanto, descargarlos más rápido desde el navegador. En archivos CSS muy grandes esto suele influir de forma considerable, por lo que es una buena práctica utilizar herramientas de minificación y reducir el tamaño del archivo CSS condensando toda su información, eliminando espacios, retornos de carro, etc...

Haciendo esto, conseguiremos que el archivo ocupe menos, pero a cambio perderemos legibilidad. Por esta razón, es habitual conservar los archivos CSS originales (sin minificar) para trabajar con ellos, mientras generamos los archivos minificados con herramientas automatizadas.

Hay que tener en cuenta que el proceso de minificación es un paso totalmente opcional, por lo que no es obligado realizarlo, pero se considera una buena práctica de optimización.

Veamos un ejemplo de un mismo archivo CSS con su contenido sin minificar y minificado:

Ejemplo de código CSS legible: index.css (96 bytes)

#main {
  background-color: black;
  color: white;
  padding: 16px;
  border: 2px solid blue;
}
Ejemplo de código CSS minificado: index.min.css (75 bytes)

#main{background-color:#000;color:#fff;padding:16px;border:2px solid #00f;}
Como se puede ver, el tamaño y la legibilidad del archivo CSS se reduce considerablemente. Al ser un archivo de tan pocas líneas, no hay demasiada diferencia, pero a medida que el archivo crece, la diferencia es mayor.

En resumen, el primer archivo es el código para humanos, el que debemos mantener y trabajar con él. El segundo archivo es el código para el navegador, que no se debe modificar directamente por humanos y que se debe generar a partir del primero.

Herramientas de minificación 
Existen múltiples herramientas para minificar código CSS. Algunas de ellas, incluso se encargan de analizar el código y, no sólo minificarlo, sino además suprimir propiedades repetidas, eliminar propiedades o valores inútiles, etc.

Veamos algunas de las más populares:

Herramienta	Modalidad	Características
CSS Nano	PostCSS	Para automatizar desde terminal o desde PostCSS.
Clean CSS	NodeJS/NPM	Para automatizar desde terminal.
CSSO	NodeJS/NPM	Optimizador de CSS (clean, compress and restructuring)
Sqwish	NodeJS/NPM	Compresor de CSS basado en Node
CSS Compressor	Online	Opciones variadas: grado de compresión, optimizaciones...
YUI Compressor	Java	Compresor CSS histórico de Yahoo
Actualmente, estos minificadores de código suelen venir incluidas en unas herramientas denominadas automatizadores o empaquetadores. Son algo más complejos y conviene profundizar en ellos cuando se tenga más conocimiento y experiencia, pero es importante tener en cuenta que realizan múltiples tareas comunes de forma automática, consiguiendo que no tengamos que preocuparnos nosotros de dichas tareas.