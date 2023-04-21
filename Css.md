# CSS (Cascading Styke Sheet)
Los estilos se pueden ponder de forma individual a cada etiqueta o de forma general desde la misma pagina html en el `head`; pero tambíen se usa desde archivos externos (css) para aplicarlos a mas de una página o archivo a la vez, y así no repetir codigo.

En css muchos atrivutos de html ahora serán tomados como etiquetas; y la definición o función de estas seran especificadas desde el propio html en el `head><link/>`.En este ejm la función seria `<style/>` sin embargo en *css* esta no será especificada a diferencia del *html*:

En *html*:

```html
    <Style>
        h1{
            color:blue;
        }
        p{
            color:white;
            background-color: crimson
        }
    </Style>
```
En *css*
```css
    h1{
        color:blue;
    }
    p{
        color:white;
        background-color: crimson
    }
```
Los elementos pueden ser cambiados de dos formas: 
* inline; q se modifican sin necesidad de separar un parrafo (son hacer salto de línea) de otro para cambiarlo, como la etiqueta *span*
* block; q separá los elemtos unos de otros (sus parrafos o lineas)para poder dar las diferentes modificaciones, como la etiqueta *div*

---
---
## Cascadeo en CSS (Hojas de estilo en cascada)

Se llaman *hojas en cascada* porque si le aplicamos a un nivel superior un style, este será aplicado desde los elementos *padre*, hasta los mas internos (elementos *hijo*); sin embargo, estos elementos pueden tener sus propios atrivutos por lo se sustituiran las configuraciones generales allí, sobreescribiendolas por las especificas 

Esta es la forma para aplicar un stylo general a todos los elementos (con `*`)de nuestra página, sin embargo, por el concepto de cascada este puede ser reemplazado al encontrar otro atributo igual pero mas interno

```css
*{
    margin: 0;
    padding: 0;
}
```

---
---
## Class (Html y Css)

Es un atributo para aplicar stylos a por medio de las clases y no por etiquetas, asi no se afectan todos los elementos q contengan esa etiqueta sino los q tengan el *class* el cual puede estar en mas de una etiqueta a la vez.(puede ser usado en diferentes valores)

En css:
```css
.tarjeta{
    border: 10px solid #560bad;
    background-color: #f1faee;
    text-align: center;
}
```
En html:
```html
    <h1 class="tarjeta">Lenguajes de Programación</h1>
    <div class="tarjeta">
        <h2>Java</h2>
        <p>Creador:James Gosling</p>
    </div>
```
---
---
## ID (Html y Css)

Atributo para dar un estilo especifico solo a una etiqueta en especifico (será usado en un solo valor)

---
---
## Box model

El box model son los marcos y son como rectangulos q separán el área entre un elemento y otro, estos espacios estan nombrados como: background, padding, border, margin; (del mas bajo hacia afuera) las medidas en *px* para estos pueden ser especificadas:
 ![box2](iman/box%20en%20la%20ventana.jpeg)
 
 
  * Si solo se especifica un valor el css la tomará como el general para cada lado
  ![box1](iman/box%20model.png)
```css
    p{
        color:white;
        background-color: crimson;
        padding: 15px;
        border: 10px solid powderblue;
        margin: 50px;
    }
```
  * Para especificar la medida para cada uno de los 4 lados se comenzara con la superior y seguira en la dirrección de las manecillas del reloj(ejm en margin); de igual forma si una medida será igual a la de su lado paralelo solo será necesario escribirla una vez, esto para simplificar (ejm en padding la 1ra=superior 2da=derecha e izquierda 3ra= inferior)(ejm border 1ra=superior e inferior 2da=derecha e izquierda)
  ```css
  p{
    color:white;
    background-color: crimson;
    padding: 40px 15px 20px;
    border: 30px 10px solid powderblue;
    margin: 40px 10px 20px 10px;
  }
  ```
  
  * Otra forma para especificar cada medida es agregando luego de la etiqueta un *top-right-bottom-left* respectivamente (ejm en margin): 

  ```css
  p{
    color:white;
    background-color: crimson;
    padding: 15px;
    border: 10px solid powderblue;
    margin-top: 40px;
    margin-right: 10px;
    margin-bottom: 20px;
    margin-left: 10px;
  }
  ```
  * Para centrar los elemetos horizontalmente; sin embargo las margenes superiores seran *0* o suprimidas con este metodo (ejm en margin):

```css
  p{
    color:white;
    background-color: crimson;
    padding: 15px;
    border: 10px solid powderblue;
    margin: auto 50px; 
   }
```

  * Para centrar nuestro texto dentro de estas margenes o rectangulos se utilizará `text-align: center;`

```css
  p{
    color:white;
    background-color: crimson;
    padding: 15px;
    border: 10px solid powderblue;
    margin: auto 50px; 
    text-align: center;
   }
```
![ejm textCenter](iman/text%20center.png)

---
---
# Estilos para link

Hay varias estados q puede tener un link; esto es necesario tenerlo en cuenta al momento de darle estilos ya q cada estado deberá ser configurado aparte:

1. Para el link en el estado antes de dar clik

```css
    a:link {
        color: #fb8500;
    }
```

2. Para el link en el estado ya visitado (despúes del clik)

```css
    a:visited{
        color: #219ebc;
    }
```

3. Para el link cuando se pone el cursor sobre este

```css
    a:hover{
    color: #8ecae6;
    }
```

4. Para el link cuando en este se mantiene oprimido el click

```css
    a:active {
    color: #023047;
    }
```
* Para darle color a cada estado de un link o `<a/>` se escribira el atributo *color* dentro del elemento al q queremos cambiar:
```css
    color: blue;
```

* Modificaciones para el decorado inferior del enlace
    1. Para quitar la linea del enlace tanto para los ya visitados como para los q no; se uitliza:
    ```css
    a:visited{
    color: #219ebc;
    text-decoration: none
    }
    ```
    2. Para poner la linea en el área inferior de los enlaces (aunque esta opción se suele activar predeterminadamente); se uitliza:
    ```css
    a:hover{
    text-decoration: underline;
    }
    ```
    3. Con los estilos correctos se podrá hacer q un link pueda parecer un boton (y ya q es un link, tambien tendria esa funcionalidad)
    ```css
    a:link, a:visited{
    background-color: #b5179e;
    color:white;
    padding: 15px 25px;
    text-align: center;
    text-decoration: none;
    }
    ```
    ![EjmLinkButton](iman/link%20style%20button.png)

    Sin embargo, al poner mas de estos se pueden sobreponer, para alinearlos de forma vertical se debe agregar: `display: inline-block;`

---
---
# Estilos en tablas 

`text-align: ;`

Para organizar texto: al centro, u otros lados

`border: 1px solid black;`

Para dar propiedades de color y ancho a los bordes o (margenes) de la tabla

`border-collapse: collapse;`

Para quitarle la doble linea a las margenes dobles q bienen por defecto en la tabla

`border-spacing: 5px;`

En caso de usar la doble linea en la tabla, este style dará la separación entre estas dos

`padding: 5px`

Para dar espacio de separación entre los textos y las margenes (Esra es la misma del *box model*)

`width: 100%;`

Especificá el espacio q ocupara respecto al ancho en relación a la página

`line-height: 70px`

Dara una separación en el área superior e inferior segun se especifique (es un tipo de `<br>`)

`nth-child(even)`

Para dar color a las celdas de la tabla, se utilizará esta propiedad especificando el *even=celdas pares* o el *odd=celdas impares*
```css
tr:nth-child(even){
    background-color: #f1faee;
}
```
---
---
# Estilos para listas

`display:block;`

Hace q esos elementos se encuntren en un tipo de bloque

`float: left;`

Para q la lista no se forme de la manera normal (vertical) sino q se organicen de izuqierda a derecha (horizontalmente)

`overflow: hidden;`

Para q la lista se muestre de manera independiente (se separe) del resto del contenido
`li a: hover`

De esta forma se especificarán los styles para las diferentes estados de los links *a*; ejm:

```css
    li a:hover{
    background-color: #1d3557;
    }
```
`ol li::before`

Esta propiedad agregará antes de cada elemento de nuestro `ol` lo q le especifiquemos en el mismo orden en q lo indiquemos

* `content: "Curso" counter(contador)`

1. Entre comillas se pondrá cualquier sigla, letra, palabra, entre otros.
2. Cambiará el color de los elementos (funcionamiento normal)
3. En countent se indicará la forma en la q se van a enumerar los `li` (esto es necesario porque al usar `::` se reemplazaran la numeración q viene por defecto en `ol.`).Ejm de como se usa correctamente:
```css
ol{
    list-style: none;
    counter-reset: contador;
}
ol li{
    counter-increment: contador;
}
ol li::before{
    content: "Curso" counter(contador);
    color: #ff6f00;
}
```

---
---
## Etiquetas

`/**/`

Para crear notas o comentarios que no veran los usuarios (lo mismo q el comentario el *html*)
```css
    /*Comentario*/
```
---
---
# Links o infografia

[Biblioteca de paleta de colores html](https://coolors.co/)