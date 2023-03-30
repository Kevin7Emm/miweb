# CSS (Cascading Styke Sheet)
Los estilos se pueden ponder de forma individual a cada etiqueta o de forma general desde la misma pagina html en el `head`; pero tambíen se usa desde archivos externos (css) para aplicarlos a mas de una página o archivo a la vez, y así no repetir codigo.

En css muchos atrivutos de html ahora serán tomados como etiquetas; y la definición o función de estas seran especificadas desde el prompio html en el `head><link/>`.En este ejm la función seria `<style/>` sin embargo en *css* esta no será especificada a diferencia del *html*:

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
---
---
## Cascadeo en CSS (Hojas de estilo en cascada)

Se llaman *hojas en cascada* porque si le aplicamos a un nivel superior un style, este será aplicado desde los elementos *padre*, hasta los mas internos (elementos *hijo*); sin embargo, estos elementos pueden tener sus propios atrivutos por lo se sustituiran las configuraciones generales allí, sobreescribiendolas por las especificas 

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