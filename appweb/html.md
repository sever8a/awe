--- 
title: HTML
summary: Referencia a las principales etiquetas básicas de HTML
authors: 
    - Jose Robledano
date: 2023-11-09
---
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

# Etiquetas básicas. La estructura

Un documento html debe comenzar siempre con las etiquetas `<!DOCTYPE html>`

De esta manera, en los primeros byte, se indica al navegador (browser) el tipo de documento que tiene que mostrar.

Las **etiquetas** se utilizan para marcar e inicio y fin de su efecto.

``` html
<div>
    texto o elementos entre las marcas
</div>
```
A su vez las etiquetas pueden tener atributos, que sirven para matizar su efecto sobre el contenido.

``` html
    <div class="titular">
        texto o elementos entre las marcas
    </div>
```


## La etiqueta html

Define una página web. Siempre debe aparecer, para comenzar la página y finalizarla. Contiene todo el resto de etiquetas y texto de la página web. 

``` html
<html>
    ...
</html>
```

Esta etiqueta contiene a otras dos.

### head

Zona de encabezado de la página. 

No es visible directamente en el navegador. 

!!! info "Algo se puede ver..."

    Algunos elementos se muestran: como el *título de la página* o el icono *favicon*, que aparece en la pestaña. 

Se indican los **metadatos** de la página web. Es decir, información adicional del documento sobre su autor, codificación, idioma ...

También aparecen las referencias globales a otros elementos de la página web (scripts, fuentes externas, hojas de estilo...). Estos contenidos pueden estar:

* **Directamente escritos** en la zona de encabezado de la página.
* **Referenciados** a otro documento que se carga cuando se visualiza la página.

La primera opción, resulta más clara y fácil de seguir, cuando se quiere conocer qué elementos incorpora la página y cuándo son utilizados.

!!! info "Encabezado **explícito**"

    *   La página ocupa más tamaño.
    * El contenido hay que actualizarlo en todas las páginas.


### body

Elemento visual de la página web. 

Todas las demás etiquetas visuales, se colocan dentro de esta.

Delimita del contenido *(texto, enlaces, imágenes...)* que forman la página web.

## Estructuras de bloque

Delimitan bloques de texto, u otros elementos.

La etiqueta más reconocible es el delimitador de párrafos **p**

### p

``` html
<p>
    Este texto, forma un párrafo. Todo el texto aparece seguido sin saltos de línea.

    Aunque al escribirlo añada separaciones.
</p>
```

El contenido queda marcado como un párrafo estableciendo un salto de línea al finalizar.

!!! info "saltos de línea"

    En el código HTML los saltos de línea del editor no tienen efecto, *al igual que los espacios en blanco extra*. Para conseguir una organización del texto, hay que utilizar etiquetas de bloque[^1] u otras etiquetas únicas[^2] especificas.

    [^1]: Las etiquetas de bloque tienen una etiqueta de inicio de bloque y otra de final de bloque.
    [^2]: Las etiquetas únicas, solo son una etiqueta de inicio, no tienen etiqueta de finalización. Aunque pueden contener atributos.

### div

Marca un bloque genérica. También tiene el efecto de salto de línea, pero puede contener todo tipo de etiquetas, *incluida su mismo tipo*.

Su efecto es similar a la etiqueta de párrafo, pero en este caso se suele utilizar para definir bloquees en el maquetado de la página web. 

Por ejemplo, el bloque central y otro bloque en el lateral izquierdo.

``` html
<div class="pagina">
    <div class="encabezado">
        Menú de opciones
    </div>
    <div class="centro">
        <p>Documento de prueba.</p>
    </div>
    <div class="pie">
        Datos de contacto
    </div>
</div>
```

### span

Marca un bloque, integrado en otro de texto. Se utilia para distinguir elementos diferentes dentro de un bloque mayor.

Por ejemplo, indicar texto en negrita dentro de un párrafo.

``` html
<p>
    Este texto, <span>forma un párrafo</span>. Todo el texto aparece seguido sin saltos de línea.

    Aunque al escribirlo añada separaciones.
</p>
```

!!! question "Etiquetas específicas para maquetado"

    Son etiquetas con función similar a las dos etiquetas anteriores, pero que se han definido de manera estándar para ocupar un espacio en el diseño.

    Por ejemplo, `menu` para definir una zona de menú, o `article` para indicar espacio para contenido textual.

    De esta forma se simplica su uso, sin necesidad de utilizar modificadores **CSS** para conseguir bloques específicos.



## Encabezados jerárquicos

Establece el nivel de encabezado de un título concreto. Se utiliza numeración baja para indicar los títulos de mayor tamaño.

``` html
    <h1>tamaño grande</h1>
    <h2>título de segundo nivel</h2>
    <h3>Título de tercer nivel</h3>
```

## Enlaces

### La etiqueta a

Enlace a otras páginas web o referencias, se utiliza la **url** para indicar el destino.

``` html
    <a href="https://www.otrolugarweb.com">Visita otro lugar de Internet</a>

    <a href="pagina2.html">Visita mi página 2<a>
```

Es necesario utilizar atributos para completar la etiqueta:

* **href** url con la que quiere enlazar. 
* **target** dónde se abrirá el enlace.Tiene varias opciones predeterminadas:
    * *_blank* en una nueva ventana.
    * *_self* en la misma ventana. Opción por defecto.
    * *_top* abre la página en pantalla completa del navegador.
    * *_parent* abre la página en iframe de la página, o la misma ventana si no hay iframe.

!!! info "Atributos"

    El atributo **target** sirve para indicar dónde se visualizará el enlace: 
    
    **_blank** en la misma ventana del navegador, o en otra nueva.


## Imágenes

### La etiqueta img

**img** es una etiqueta única, no necesita ser cerrada.

Toda los datos necesarios se indican mediante **atributos**:
* **src**, indica la ruta origen de la imagen. Puede ser una ruta externa (indicando el domínio de otra web), o una ruta relativa a la organización de los ficheros de la propia página.

* **alt**, texto alternativo que describe la imagen, se muestra si no es posible mostrar la imagen.

Ejemplo:

``` html
    <img src="carpeta_imagenes/miimagen.jpg" alt="un pingüino en mi ascensor">
```

!!! question "Sintaxis"

    Observa que los parámetros de los atributos deben ir entre comillas.


## Listas

Son enumeraciones de elementos.

Hay tres tipos de listas: las numeradas, sin numerar y de definición (o diccionario).

``` html
<div>
    <ul>
        <li>Un elemento</li>
        <li>Otro elemento</li>
        <li>Úlitmo elemento</li>
    </ul>
</div>
```
!!! info "Atributo específico"

    Las listas desordenadas pueden utilizar el atributo **type** con las siguientes opciones:
    
    * **disc** muestra un círculo o punto.
    * **square** muestra un cuadrado.
    * **circle** muestra un círculo sin rellenar.


``` html
<p>
    Ejemplo de lista numerada.
    <ol>
        <li>primera opción</li>
        <li>segunda opción</li>
        <li>tercera opción</li>
    </ol>
</p>
```
!! info "Atributos listas ordenadas"

    Hay unos atributos específicos para las listas ordenadas, que permiten modificar la presentación: **reversed**, **start**, **type**.


Listas de definición.

``` html
<div>
    <dl>
        <dt>Atributo</dt>
        <dd>Modificador del efecto de la etiqueta.</dd>
        <dt>Etiqueta</dt>
        <dd>Elemento que marca el inicio y fin de un efecto sobre los caracteres incluidos.</dd>

    </dl>
</div>
```