# HTML: Uno para controlarlos a todos

**HTML5** es el último estándard de un lenguaje de marcas que permite mostrar contenido hipermedia en todos los navegadores. Un gran acuerdo entre todos los desarrolladores más importantes, que ha supuesto un cambio en la anterior tendencia competitiva para dominar el mercado.

!!! question "Confusion competitiva"

    Cada creador de cada navegador *(Microsoft, Netescape, Google, Opera, ...)* generaba sus propias etiquetas para mostar algunos elementos.

    Esto suponía para los desarrolladores de páginas web, tener que incluir diferentes versiones de fragmentos de código válido para cada uno de los navegadores.

Tutorial de referencia [para conocer el estandar HTML5](https://www.w3schools.com/html/).

# Principios del lenguaje HTML

Se trata de un conjunto de etiquetas, que se colocan formando bloques. Cada etiqueta tiene un valor semántico, que **establece** la función de ese elemento en el conjunto de la página web.

``` html
    <html>
        <head>
            <title>
                Saludo
            </title>
        </head>
        <body>
            Hola mundo!!
        </body>
    </html>

```

# Etiquetas básicas

## html

Define una página web. Siempre debe aparecer, para comenzar la página y finalizarla. Contiene todo el resto de etiquetas y texto de la página web. 

``` html
<html>
    ...
</html>
```

## head

Zona de encabezado de la página. Son datos que no se muestran en la página web *excepto el título de la etiqueta*. Se utiliza para colocar las referencias a otros contenidos de la página web (scripts, fuentes externas, hojas de estilo...)

## body

Elemento visual de la página web. Delimita del contenido *(texto, enlaces, imágenes...)* que forman la página web.

## p

Delimitador de párrafo. El contenido queda marcado como un párrafo estableciendo un salto de línea al finalizar.

!!! info "saltos de línea"

    En el código HTML los saltos de línea del editor no tienen efecto, *al igual que los espacios en blanco extra*. Para conseguir una organización del texto, hay que utilizar etiquetas de bloque[^1] u otras etiquetas únicas[^2] especificas.

    [^1]: Las etiquetas de bloque tienen una etiqueta de inicio de bloque y otra de final de bloque.
    [^2]: Las etiquetas únicas, solo son una etiqueta de inicio, no tienen etiqueta de finalización. Aunque pueden contener atributos.

## div

Marca un bloque. Su efecto es similar a la anterior etiqueta. Se suele utilizar para definir bloquees en el maquetado de la página web. 

Por ejemplo, el bloque central y otro bloque en el lateral izquierdo.


## span

Marca un bloque, integrado en otro de texto. Se utilia para distinguir elementos diferentes dentro de un bloque mayor.

Por ejemplo, indicar texto en negrita dentro de un párrafo.

!!! question "Etiquetas específicas para maquetado"

    Son etiquetas con función similar a las dos etiquetas anteriores, pero que se han definido de manera estándar para ocupar un espacio en el diseño.

    Por ejemplo, `menu` para definir una zona de menú, o `article` para indicar espacio para contenido textual.

    De esta forma se simplica su uso, sin necesidad de utilizar modificadores **CSS** para conseguir bloques específicos.