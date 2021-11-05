# Google-Clone
Este proyecto está hecho gracias al [Curso Práctico de HTML y CSS](https://platzi.com/clases/html-practico/) de Diego De Granda en [Platzi](https://platzi.com/)

## Partes del proyecto
### Header
El header se compone por una etiqueta `nav`, ya que se necesitaba tener una lista de links. Esta lista de links será una lista desordenada, es decir, contrendá una etiqueta `ul` y dentro de esta etiqueta se irán añadiendo etiquetas `li` con el nombre de los links dentro de una etiqueta `a`. Parece un poco complicado, pero tal vez el código de abajo te aclare un poco.
~~~html
  <nav>
      <ul class="nav-right-section">
          <li><a href="link">Gmail</a></li>
          <li><a href="link">Imágenes</a></li>
          <li class="menu-icon"><a href=""></a></li>
          <li><a href=""><img src="link" alt="My Avatar"></a></li>
      </ul>
  </nav>
~~~
El HTML de arriba se ve de la siguiente forma:

![header](https://i.imgur.com/ANskqEU.png)

Como puedes ver no se parece mucho al header de Google, pero no te preocupes, porque eso se puede arreglar con un CSS.

~~~css
header{
    width: 100%;
    height: 60px;
}
header nav{
    display: flex;
    justify-content: flex-end;
}
header nav .nav-right-section{
    width: 250px;
    height: auto;
    display: flex;
    list-style: none;
    justify-content: flex-end;
    align-items: center;
    margin-right: 0.5%;
}
nav .nav-right-section a{
    margin-right: 15px;
    color: #222;
}

nav .nav-right-section .menu-icon{
    background-image: url("link");
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    margin-right: 10%;
    margin-left: 10%;
}
nav .nav-right-section img{
    border-radius: 50%;
}
~~~
Sé que puede parecer muy complicado el código por ahora, pero lo que se utilizo en el `header`fue para que tuviera el tamaño del ancho de la página y que su altura no superara los 60px. Además en el `nav` se utilizó `flex` y `flex-end`. Esto para que lo que estuviera al interior del `nav` estuviera a la derecha.

Para la clase `nav-right-section` se le quitaron los estilos a las listas, esto para evitar que aparecieran los puntos, se le agregó un pequeño margen a la derecha y al igual que el `header`, se utilizó `flex-end` para que los items se movieran a la derecha. Para los `a` de la clase `nav-right-section` se les agregó un margen a la derecha para que estuvieran separados unos de otros y también se les cambió el color de las letras.

Para la clase `menu-icon` se agregó la imagen del menú de Google y también un pequeño margen a la derecha y a la izquierda para que estuviera más separada de los demás items. Y por último, a la imagen del avatar se le agregó un `border-radius: 50%` para redondear la imagen.

¡Y listo, ya tienes tu header de Google!
![header-css](https://i.imgur.com/nUMb0SA.png)
### Main
El main se puede dividir en tres partes:
#### Logo
La sección del logo es bastante simple, es una etiqueta `section` con una clase `main-logo`, y dentro de esta etiqueta se incluye una etiqueta `img` con un link a la imagen del logo de Google.
~~~html
  <section class="main-logo">
      <img src="link" alt="Logo de Google">
  </section>
~~~
![main](https://i.imgur.com/J8b2ayQ.png?1)

Pero esto solo muestra la imagen en el lado izquierdo de la página y no es del tamaño deseado. Así que con el CSS centramos el contenido de `main` con `text-align:center` y con `width` en la clase `main-logo` definimos el tamaño de la sección y con `margin` logramos centrar el contenido, en este caso la imagen. También le agregamos un `margin-bottom` para que haya una distancia entre el logo y el buscador de la siguiente sección. Y por último se le agrega estilo a `.main-logo img` para definir las dimensiones del `height` y `width`.
~~~css
main {
    text-align: center;
}
main .main-logo{
    width: 530px;
    margin: 0 auto;
    margin-bottom: 1.8%;
}
main .main-logo img{
    height: 92px;
    width: 272px;
}
~~~
#### Buscador
La sección del buscador es un poco más extensa, esto debido a que el buscador posee imágenes en su interior. Para esto se creará una etiqueta `section` de clase `main-input`, y dentro de esta habrá un div con clase `main-input-container`, que en su interior tendrá una etiqueta `span` con clase `search-icon`, la cual servirá para agregar la imagen de lupa que posee el buscador de google. También se creará una etiqueta `input` de tipo texto y una etiqueta `a` con clase `micro-icon`, esto servirá para agregar la imagen del micrófono que posee el buscardor de google.
~~~html
  <section class="main-input">
      <div class="main-input-container">
          <span class="search-icon"></span>
          <input type="text">
          <a class="micro-icon" href=""></a>
      </div>
  </section>
~~~
Como puedes ver el buscador es un rectángulo que no tiene ninguna imagen y que está en el lado izquierdo de la pantalla. Además si pasas el mouse por encima no pasa nada.

![main](https://i.imgur.com/ueedrsk.png?1)

Pero no te preocupes, que para eso está el CSS. Primero modificamos la clase `main-input` para que tenga un ancho de 45% y un margen de `0 auto` (esto se utiliza para que quede centrado), y además una altura de 42px (porque tampoco queremos un buscardor tan grande). 
~~~css
main .main-input {
    width: 45%;
    margin: 0 auto;
    margin-bottom: 30px;
}
~~~
Ahora por fin toca embellecer el buscador, se modifica la clase `main-input-container` para que tenga un ancho de 100% (como está dentro de la clase `main-input`, el 100% de esta clase es el total de su clase contenedora, o sea el 45% de la página) y una altura de auto. También se le agrega un borde con `border` y `border-radius`, para que de la ilusión de que `main-input-container` es realmente un input.

Con `main-input-container:hover`se implementará lo que ocurrirá cuando el mouse esté por encima de `main-input-container`. En este caso con `box-shadow` se crea una especie de sombra difuminada y con `border-color` se cambia el color del borde del `section` a un gris muy claro para hacer más notorio `box-shadow`.
~~~css
main .main-input-container{
    width: 100%;
    border-radius: 100px;
    border: 1px solid #d8d8d8;
    display: flex;
    justify-content: center;
    align-items: center;
}
main .main-input-container:hover{
    box-shadow: 0 1px 6px 0 #c2c2c2;
    border-color: #eeeeee;

}
~~~

Primero al estilizar el `input` se le modifica su ancho, ya que el buscador tiene dos imágenes a cada lado, por lo que la parte en la que se escribe debe de ser más pequeña que su conteneder. Para esto se utilizó un `width: 86%` y `height: 42px`. También se le eliminaron los bordes con `border: none` y los bordes que aparecen cuando se escribe en el `input` con `outline: none`.
~~~css
main .main-input input{
    width: 86%;
    height: 42px;
    border: none;
    outline: none;
}
~~~

Para agregar las imagenes del buscador de hace de formas parecidas, en ambas clases `search-icon` y `micro-icon` se utiliza `background-image` para agregar la imágen que van a contener de fondo, `background-repeat` se utiliza para repetir o no la imagen y se le agrega `no-repeat` para que no lo repita. 

Se utiliza `background-position` para elegir en qué posición se quiere que esté la imagen de fondo, en este caso en el centro. Y por último `background-size` que pregunta de qué tamaño debe ser la imagen de fondo,  en mi caso elegí que el tamaño de quién lo contiene. Por ahora solo falta elegir el tamaño del contenedor, como son imagenes cuadradas fueron de 17px y 24px respectivamente para cada imagen.

A `micro-icon` se le agregó `cursor: pointer`, esto se utiliza para que se vea el cursor cuando se pasa el mouse. En mi caso se debe ver una mano blanca y pequeña, depende de la configuración de tu computador se puede ver de otra forma.

~~~css
main .main-input .search-icon{
    background-image: url("link");
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    width: 17px;
    height: 17px;
}
main .main-input .micro-icon{
    background-image: url("link");
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    width: 24px;
    height: 24px;
    cursor: pointer;
}
~~~

#### Botones de búsqueda
Para los botones de búsqueda se crea un `section` con la clase `main-buttons`, esto para facilitar centrarlos con el CSS. Cada botón debe estar dentro de un `div`.

~~~html
  <section class="main-buttons">
      <div>
          <button>Buscar con Google</button>
      </div>
      <div>
          <button>Me siento con suerte</button>
      </div>
  </section>
~~~
Además de que igual a todo lo demás los botones están al lado izquierdo de la pantalla y que están uno sobre el otro en vez de uno a cada lado, estos son muy pequeños y los colores no son iguales a los que utiliza Google.

![main](https://i.imgur.com/AGKL7M4.png?1)

Para poder centrar los botones se debe crear la clase `main-buttons` y modificar `margin`, además se le agrega un ancho máximo de 530px.
A `main-buttons div` se le aplica `display: inline-block` para hacer que los botones estén uno al lado del otro.
~~~css
main .main-buttons{
    width: 530px;
    margin: 0 auto;
}
main .main-buttons div{
    display: inline-block;
}
~~~

Ahora que ya se logró que ambos botones estén uno al lado del otro toca hacer que se parezcan a los botones de Google. Con `height` se modifica la altura, `background-color` le modifica el color de fondo, `border` modifica los bordes que trae por defecto la etiqueta de HTML, `font-size` y `color` cambia el tamaño de la letra y el color respectivamente, `border-radius` produce las curvas de las esquinas, `padding` es el espacio entre el borde del botón y lo que está en su interior, y por último `margin-right` que separa 15px el botón de lo que tenga a su derecha.

~~~css
main .main-buttons button{
    height: 36px;
    background-color: #fafafa;
    border: 0;
    font-size: 14px;
    color: #505050;
    border-radius: 5px;
    padding: 0 15px; 
    margin-right: 15px;
}
~~~

Ahora toca realizar el `hover`, esto es lo que pasa cuando pasas el cursor sobre los botones. Tal vez no lo haz notado, pero aparece un pequeño borde y cambia el color del texto. Así que manos a la obra con el CSS.

Primero utilizamos `border`, con esto cambiamos el borde de 0 a 1px, le decimos que queremos que sea de tipo solid y además le agregamos un color. Con `box-shadow` al igual que se hizo más adelante se crea una especie de sombra difuminada. Con `color` se cambia el color del texto y con `background-color` el color del fondo del botón, además con `cursor: pointer` muestra el cursor cuando se pase el cursor por sobre el botón.

~~~css
main .main-buttons button:hover{
    border: 1px solid #c6c6c6;
    box-shadow: 0px 1px 1px rgba(0,0,0,0.1);
    color: #222;
    background-color: #f8f8f8;
    cursor: pointer;
}
~~~

Y gracias a todos lo CSS que ya se crearon pasamos de esto:

![main](https://i.imgur.com/J8b2ayQ.png)

A esto:

![main with css](https://i.imgur.com/NmFjohA.png)

Un cambio bastante grande, pero no es nada comparado con lo que se hará ahora con el `Footer`.

### Footer
El `footer` se puede dividir en tres partes; la sección del país, una lista de links que se hubica en la parte de abajo a la derecha y otra lista de link, la cual una contiene un sub menú. Además de esto el footer siempre ha de verse, aunque sea necesario hacer scroll. Esto lo logré gracias a `position: absolute`.

~~~css
footer{
    width: 100%;
    position: absolute;
    bottom: 0;
    background-color: #f2f2f2;
}
~~~

Lo primero que aparece en el `footer` es el país del usuario, en mi caso es Chile así que lo agregué con una etiqueta `p` y le cree la clase `footer-pais` para poder modificarlo más adelante.

~~~html
  <p class="footer-pais">Chile</p>
~~~

![footer](https://i.imgur.com/LfaTj2c.png?1)

Hasta ahora ya debes conocer lo que hacen las siguientes propiedades de CSS, por esto me daré el gusto de solo explicarte lo que no he explicado antes. Por ejemplo, `border-bottom` que funciona igual que `border` solo que en vez de hacer un borde en toda la etiqueta, lo hace solo en la parte de abajo. También está `font-family` que selecciona la fuente, en este caso arial y si el navegador no soporta este tipo de letra entonces elegirá sans-serif.
~~~css
footer .footer-pais{
    height: 49%;
    font-size: 14px;
    border-bottom: 1px solid #dbdbdb;
    color: #7a7a7a;
    padding-left: 1.5%;
    font-family: arial,sans-serif;
    font-size: 15px;
    padding-bottom: 1%;
    padding-left: 3%;
}
~~~
***
 Antes de comenzar con la siguiente parte, necesitas saber que ambas clases que te muestro a continuación están dentro de un `div`. Este lo utilicé para generar las dos columnas gracias a `display: grid` y `grid-template-columns: 1fr 1fr`.

~~~css
footer div{
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    margin: 1.1% auto;
}
~~~
***
Lo segundo que se puede apreciar es una lista de links que estará hubicado en el lado esquierdo del `footer`, es por esto que se creó la clase `footer-left`.
~~~html
  <ul class="footer-left">
      <li><a href="link">Sobre Google</a></li>
      <li><a href="link">Publicidad</a></li>
      <li><a href="link">Negocios</a></li>
      <li><a href="link">Cómo funciona la Búsqueda</a></li>
  </ul>
~~~
![footer](https://i.imgur.com/eUnByjU.png?1)

Vaya, ya casi no hay cosas que no te haya explicado ya. `text-decoration` se refiere a la linea que tiene el link, es este caso yo quiero que se subraye cada vez que paso el cursor sobre una etiqueta `a` que está dentro de una etiqueta `li` y que a su vez esta está contenida en un `lu`.
~~~css
footer ul{
    margin: auto 10px;
    display: flex;
    list-style: none;
    padding-left: 0;
}
footer ul>li>a{
    margin: 10px 15px;
    color: #7a7a7a;
    font-size: 14px;
}
footer ul>li>a:hover{
    text-decoration: underline;
}
~~~
La clase `footer-left` solo hace que `ul` quede al lado izquierdo, es decir, se justifique a la izquierda. Como quedaba muy cerca del lado izquierdo le agregué un `margin-left` para asegurarme de que quedara exactamente donde lo quería.

~~~css
footer .footer-left {
    justify-self: left;
    margin-left: 4%;
}
~~~

El `footer-right` se puede poner un poco más complicado, al igual que en `footer-left` se creó una lista desorganizada con etiquetas `a` en su interior, pero a diferencia de este se creó otra lista desorganizada dentro de una de las etiquetas `li`. Esto se hizo para crear el sub menú que tiene "Preferencias", así que como supondrás esta clase de lista desorganizada se llama `footer-sub-menu`.
~~~html
 <ul class="footer-right">
      <li><a href="link">Privacidad</a></li>
      <li><a href="link">Condiciones</a></li>
      <li><a href="#">Preferencias</a>
          <ul class="footer-sub-menu">
              <li><a href="link" target="_blank ">Configuración de búsqueda</a></li>
              <li><a href="link" target="_blank ">Búsqueda avanzada</a></li>
              <li><a href="link">Tus datos en la búsqueda</a></li>
              <li><a href="link" target="_blank ">Historial de búsqueda</a></li>
              <li><a href="link" target="_blank ">Buscar en la ayuda</a></li>
              <li><a href="#">Enviar comentarios</a></li>
          </ul>
      </li>
  </ul>
~~~

Como puedes apreciar hay una lista dentro de otra lista, esto muy pronto va a cambiar. Lo que se necesita hacer es mover la lista a un punto exacto de la página que será sobre "Preferencias" y además se necesita de que esta sub lista no sea visible hasta que se pase el cursor sobre "Preferencias".

![footer](https://i.imgur.com/je1yMYq.png?1)

Al igual que la clase anterior, `footer-right` utiliza `justify-self` pero esta vez para justificarse haciea el lado derecho de la pantalla.
Como dije antes se necesita posicionar el sub menú en una posición específica de la pantalla, esto se logra con `position: absolute`, `right` y `bottom`. Además de esto es necesario aplicar `display: none` para que el menú esté oculto hasta que lo necesitemos.

Para las etiquetas `li` dentro del sub menú se les agregó un margen y además `display: block` para que el sub menú aparezca cada vez que se pase el cursor sobre "Preferencias".

~~~css
footer .footer-right{
    justify-self: right;
}
.footer-sub-menu {
    position: absolute;
    display: none;
    width: inherit;
    right: 0.5%;
    bottom: 49%;
}
.footer-sub-menu li{
    margin: 13% auto;
}

div li:hover ul {
    display: block;
    background-color: #ffffff;
    border: 1px solid #70757a;
}
~~~ 
***
Aclaranción: Soy consciente de que el sub menú se muestre cuando se pase el cursor sobre "Preferencias" no es lo mejor. Tuvo que hacerse con JavaScript, pero como este es un reto de HTML y CSS se dejó de esa forma.
***

Y con estos tres partes del footer terminadas, pasamos de estos:

![footer](https://i.imgur.com/OZFLXsI.png)

A esto:

![footer with css](https://i.imgur.com/3K4Tfg2.png)

Muchas gracias por llegar hasta este punto. Por aquí abajo encontrarás el link a la página web. Siéntete libre de hacer un fork y jugar con el proyecto. 

## Link
Link para ver [Mi Google Clone](https://camilu-png.github.io/Google-Clone/). 

![HTML](https://img.shields.io/badge/HTML-orange?style=plastic) ![CSS](https://img.shields.io/badge/CSS-blue?style=plastic)
## TODO
### Sub Menú
Falta mejorar el sub-menú de "Preferencias", la idea es que al hacer click sobre "Preferencias" se despliegue el sub-menú y al clickear fuera de este desaparesca.
### Responsive Design
Por ahora se parece a Google, pero esto es solo desde el computador. Se necesita habilitar para celular.