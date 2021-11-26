# Imágenes y Objetos en CSS
Al insertar en un documento HTML algunos objetos como imágenes a través de la etiqueta <img>, elementos multimedia a través de <video> u otros como <textarea> o <input>, dichos elementos tienen su propia forma de mostrarse en pantalla ya que tienen características ajenas a CSS. Por dicha razón, muchas veces tienen un tamaño inicial que no encaja con el uso que queremos darle, no se adapta a las cajas o contenedores que usamos o no funciona como tenemos previsto que lo haga.

Sin embargo, existen algunas propiedades en CSS que nos permiten modificar ciertos aspectos de estos elementos, pudiendo darle estilo y adaptarlos. Aquí puedes ver una tabla de resumen de las propiedades que vamos a ver:

Propiedad	Valores	Descripción
object-fit	fill | contain | cover | none | scale-down	Modo de relleno del elemento.
object-position	 	Posición (x,y) del elemento.
image-rendering	auto | smooth | high-quality | crisp-edges | pixelated	Algoritmo de escalado a utilizar.
image-orientation	from-image | none |  [flip]	Orientación de la imagen.
aspect-ratio	auto |  /  | 	Define la proporción de aspecto.
La propiedad object-fit 
La propiedad object-fit nos va a permitir cambiar el modo en el que se rellena una imagen <img> (o cualquier otro objeto de representación externa a CSS) en su contenedor padre. Los valores que puede tomar dicha propiedad son los siguientes:

Valor	Descripción
fill	Rellena la imagen en el espacio del contenedor padre. Habitualmente, estirando la imagen.
contain	Mantiene el aspecto natural conteniendo el máximo posible de la imagen.
cover	Mantiene el aspecto natural cubriendo el contenedor padre, de modo que no hayan huecos sin cubrir.
none	Mantiene el aspecto natural.
scale-down	Similar a none o contain, escalando hacia abajo.
Imaginemos que una imagen, que tiene su propio tamaño, es notablemente superior a los elementos contenedores que la van a contener. Por defecto, la imagen tiene su propio tamaño y se desbordará, pero nos podría interesar cambiar el tamaño para que se adapte al contenedor padre. Para ello, utilizaremos los diferentes valores de la propiedad object-fit:

La propiedad Object-fit CSS

Así pues, podemos plantear el siguiente código de ejemplo, donde se puede utilizar la propiedad object-fit con sus diferentes valores y comprobar como se comporta:

Code
Preview
CodePen
<div class="parent">
  <div class="item"><img src="http://placekitten.com/500/300"></div>
  <div class="item"><img src="http://placekitten.com/100/400"></div>
  <div class="item"><img src="http://placekitten.com/300/200"></div>
  <div class="item"><img src="http://placekitten.com/300/300"></div>
</div>

<style>
.parent {
  display: flex;
}
.item {
  margin: 10px;
  width: 150px;
  height: 150px;
  background: lightgrey;
}
img {
  width: 100%;
  height: 100%;
  object-fit: fill;
}
</style>

La propiedad object-position 
Además, tenemos la propiedad object-position que nos sirve para utilizar junto a la propiedad object-fit y cambiar la posición donde aparece la imagen, especialmente cuando está recortada y sólo aparece un fragmento o parte de la imagen. La propiedad funciona de forma muy parecida a como lo hace la propiedad background-position:

Valor	Descripción
50% 50%	Por defecto, la imagen está centrada tanto en X como en Y.
 	Se puede indicar un porcentaje para colocarlo en el eje correspondiente.
También se pueden indicar palabras clave como top, left, right, bottom o center para indicar en que zona quieres centrar la imagen, incluso, añadiendo un porcentaje tras ellos para ajustar más concretamente:

.element img {
  object-fit: cover;
  object-position: left 20% top 25%;
}
La propiedad image-rendering 
La propiedad image-rendering permite indicar al navegador como se debería renderizar una imagen, y más concretamente, que algoritmo de reescalado se debería aplicar. Por lo general, este valor lo utilizará correctamente el navegador, pero en algunas situaciones, al cambiar de tamaño a ciertas imágenes, es posible que se vean con una menor calidad o con defectos como bordes borrosos o ciertas imperfecciones.

Con la propiedad image-rendering indicamos al navegador que sistema de reescalado debe utilizar, algo muy interesante cuando utilizamos por ejemplo, imágenes pixel art, donde nos interesa que se utilicen algoritmos como nearest neighbour (vecinos más próximos) que respeta y preserva la definición del pixel art.

Los valores que puede tomar la propiedad son los siguientes:

Valor	Descripción
auto%	Por defecto, el navegador decide que algoritmo de escalado utilizar.
smooth	La imagen es escalada con algoritmos que priorizan la apariencia, ideal para fotos.
high-quality	Idéntico a smooth, pero con mejor calidad. Utilizar cuando la calidad se degrada.
crisp-edges	Enfocado en preservar contrastes y bordes de imagen. Ideal para lineas definidas y bocetos.
pixelated	Usa algoritmo de "vecinos más próximos", orientado a preservar pixel art bien definido.
Aquí puedes ver, por ejemplo, la diferencia de aplicar image-rendering con los valores crisp-edges y pixelated respectivamente a una imagen orientada para representar un dibujo pixel art. Como se observa, el Super Mario de la derecha tiene los bordes mucho más definidos que el Super Mario de la izquierda, el cuál se ve más borroso:

La propiedad image-rendering en CSS

Hoy en día, la compatibilidad entre navegadores de esta propiedad es muy buena, salvo Internet Explorer, que usa valores no estándares.




La propiedad image-orientation 
La propiedad image-orientation permite rotar una imagen respecto a la información que se encuentra en sus metadatos, o por el contrario, desactivarla y mostrarla tal cuál aparece en la propia imagen. Los valores que se pueden indicar son los siguientes, donde from-image es el valor por defecto:

Valor	Descripción
from-image	Usa la orientación de la imagen indicada en sus metadatos EXIF.
none	No se usa ninguna rotación adicional. Se muestra tal cual.
La propiedad aspect-ratio 
La propiedad aspect-ratio permite cambiar la proporción de aspecto width / height de una imagen u objeto desde CSS. De esta forma, podemos asegurarnos de que las imágenes no se deformarán o tendrán una relación de aspecto no adecuada en nuestras páginas.

Los valores de la propiedad aspect-ratio son:

Valor	Descripción
auto	El navegador calcula automáticamente la proporción adecuada.
 / 	Se utilizará la proporción width / height indicada.
auto  / 	Utiliza la proporción indicada, salvo que tenga un tamaño definido.
Actualmente, el soporte es bueno, con la excepción de Safari, que no lo implementa.