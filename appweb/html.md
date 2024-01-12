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

    Cada creador de cada navegador *(Microsoft, Netescape, Google, Opera, ...)* generaba sus propias etiquetas para mostar algunos elementos. Por ejemplo, para reproducir un sonido, cada navegador tenía su propia etiqueta.

    Esto suponía que los desarrolladores de páginas web, tenían que incluir diferentes versiones de fragmentos de código válido para cada uno de los navegadores.

Tutorial de referencia [para conocer el estandar HTML5](https://www.w3schools.com/html/).

# Principios del lenguaje HTML

Se trata de un conjunto de etiquetas, que se colocan formando bloques. Cada etiqueta tiene un valor semántico, que **establece** la función de ese elemento en el conjunto de la página web.

Un **bloque** comienza con una etiqueta y se cierra donde vuelve a aparecer la misma etiqueta precedida de **/**. Entre medio puede haber cualquier cantidad y tipo de carácteres.

Las etiquetas delimitan donde aplican su efecto. Para comenzar se utiliza la forma  **<etiqueta>** y para finalizar su efecto **</etiqueta>**.

A su vez las etiquetas pueden anidarse incluyendo unas dentro del efecto de otras.

También es importante cuidar que la primera etiqueta que se abra debe ser la última en cerrarse. Manteniendo esta regla se evitan los efectos cruzados.

!!! question "HTML robusto"

    El lenguaje de marcas HTML es robusto en el sentido que si se comete algún error en el código, siempre intenta mostrar lo posible.

    Por ejemplo si olvidamos cerrar una etiqueta, el efecto se extenderá hasta final del documento.

!!! info "Etiquetas y efecto"

    Las **etiquetas** se utilizan para marcar el inicio y fin de su efecto.

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
A su vez las etiquetas pueden tener atributos, que sirven para matizar el efecto de la etiqueta sobre el contenido.

``` html hl_lines="1"
    <div class="titular">
        texto o elementos entre las marcas
    </div>
```
Por ejemplo, la etiqueta **```<a>```** para crear un enlace, necesita la información de la nueva dirección a la que va a redirigir la navegación. Esta información se pasa en el parámetro **href** *hiperreferencia*.

``` html hl_lines="2"
    ...
    <a href="https://www.aprendehtml.com">
    ---
```

# Etiquetas básicas. La estructura

Un documento html debe comenzar siempre con las etiquetas `<!DOCTYPE html>`

De esta manera, en los primeros byte de una página web, se indica al navegador (browser) el tipo de documento que tiene que mostrar.

Tiene una estructura jerárquica o de árbol, donde una etiqueta actúa como nodo raiz, y el resto están contenidas en estas.



``` html
<div>
    texto o elementos entre las marcas
</div>
```

## Una página un bloque. La etiqueta **html** 

Define una página web. Siempre debe aparecer, para comenzar la página y finalizarla. Contiene todo el resto de etiquetas y texto de la página web. Es la **etiqueta raiz** de la estructura de la página web.

``` html hl_lines="1 8"
<html>
    <title>
        ---
    </title>
    <body>
        ---
    </body>
</html>
```

Esta etiqueta siempre contiene a otras dos.

## Primera informacion de la página. Etiqueta **head**

El contenido colocado en esta etiqueta no es visible directamente en el navegador. Es un espacio donde se colocan los **metadatos**, necesarios para que los buscadores encuentren la página web. 

!!! info "Algo se puede ver..."

    Algunos elementos se muestran: como el *título de la página* o el icono *favicon*, que aparece en la pestaña. 

Algunos **metadatos** de la página web: información adicional del documento sobre su autor, codificación, idioma, keywords ...

También se colocan las referencias a **otros elementos externos o internos** que se utilizan en la página web (scripts, fuentes externas, hojas de estilo...). Estos contenidos pueden estar:

* **Internos** aparecen escritos directamente en la zona de encabezado de la página.
* **Externos** referencias a otro documento que se carga cuando se visualiza la página.

La primera opción, resulta más clara y fácil de seguir, cuando se quiere conocer qué elementos incorpora la página y cuándo son utilizados. 

Pero referenciar a un documento externo permite separar la presentación del negocio y facilita la edición y adaptación de la página web.

!!! info "Encabezado **explícito**"

    * La página ocupa más tamaño. Contiene más caracteres.
    * El contenido hay que actualizarlo en todas las páginas.


## Todo lo visible. Etiqueta **body**

Contiene toda la parte visual de la página web. 

Todas las demás etiquetas visuales, se colocan dentro de esta.

La esencia del hipertexto en las páginas web se basa en la utilización de texto que contiene enlaces a otros téxtos **los hiperenlaces**. 
Estos junto al *texto, enlaces, imágenes y otros elementos multimedia* forman el contenido de la página web.

``` html hl_lines="2 4"
<html><head></head>
<body>
    Zona donde se coloca el resto de etiquetas visuales y texto plano.
</body>
</html>
```

!!! info "Etiquetas de estructura"

    Las etiquetas de estructura **html**, **head** y **body** solo pueden aparecer una vez en la página web.



## Estructuras de bloque

Delimitan bloques de texto, u otros elementos.

La etiqueta más reconocible es el delimitador de párrafos **p**

### **p**

``` html hl_lines="1 5"
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

### **div**

Marca un bloque genérico. También tiene el efecto de salto de línea, pero puede contener todo tipo de etiquetas, *incluida su mismo tipo*.

Su efecto es similar a la etiqueta de párrafo, pero en este caso se suele utilizar para definir bloques o cajas en el maquetado de la página web. 

Por ejemplo, el bloque central y otro bloque en el lateral izquierdo.

``` html hl_lines="2 4 5 7"
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

### **span**

Marca un bloque, integrado en otro de texto. Se utilia para distinguir elementos diferentes dentro de un bloque mayor.

Por ejemplo, indicar texto en negrita dentro de un párrafo.

``` html hl_lines="2"
<p>
    Este texto, <span>forma un párrafo</span>. Todo el texto aparece seguido sin saltos de línea.

    Aunque al escribirlo añada separaciones.
</p>
```

!!! question "Etiquetas específicas para maquetado"

    Son etiquetas con función similar a las dos etiquetas anteriores, pero que se han definido de manera estándar para ocupar un espacio en el diseño.

    Por ejemplo, `menu` para definir una zona de menú, o `article` para indicar espacio para contenido textual.

    De esta forma se simplica su uso, sin necesidad de utilizar modificadores **CSS** para conseguir bloques específicos.



## Encabezados jerárquicos **h1**

Establece el nivel de encabezado de un título concreto. Se utiliza numeración baja para indicar los títulos de mayor tamaño.

``` html
    <h1>tamaño grande</h1>
    <h2>título de segundo nivel</h2>
    <h3>Título de tercer nivel</h3>
```
Los valores que acompañan a la letra h en la etiqueta, indican el tamaño del título. Un valor más alto, es un título de menos importancia.

## Enlaces. La etiqueta **a**

Para enlazar con otras páginas web o referencias, se utiliza la **url** para indicar el destino.

``` html hl_lines="1"
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


## Imágenes. La etiqueta **img**

**img** es una etiqueta única, que no necesita ser cerrada.

Toda los datos necesarios se indican mediante **atributos**:
* **src**, indica la ruta origen de la imagen. Puede ser una ruta externa (indicando el domínio de otra web), o una ruta relativa a la organización de los ficheros de la propia página.

* **alt**, texto alternativo que describe la imagen, se muestra si no es posible mostrar la imagen.

Ejemplo:

``` html hl_lines="1"
    <img src="carpeta_imagenes/miimagen.jpg" alt="un pingüino en mi ascensor">
```

!!! question "Sintaxis"

    Observa que los parámetros de los atributos deben ir entre comillas.


## Listas

Son enumeraciones de elementos.

Hay tres tipos de listas: 
- Numeradas.
- Sin numerar
- De definición (o diccionario).

``` html hl_lines="2 6"
<div>
    <ul>
        <li>Un elemento</li>
        <li>Otro elemento</li>
        <li>Último elemento</li>
    </ul>
</div>
```
!!! info "Atributo específico"

    Las listas desordenadas pueden utilizar el atributo **type** con las siguientes opciones:
    
    * **disc** muestra un círculo o punto.
    * **square** muestra un cuadrado.
    * **circle** muestra un círculo sin rellenar.


``` html hl_lines="3 7"
<p>
    Ejemplo de lista numerada.
    <ol>
        <li>primera opción</li>
        <li>segunda opción</li>
        <li>tercera opción</li>
    </ol>
</p>
```
!!! info "Atributos listas ordenadas"

    Hay unos atributos específicos para las listas ordenadas, que permiten modificar la presentación: **reversed**, **start**, **type**.


Listas de definición.

``` html hl_lines="2 8"
<div>
    <dl>
        <dt>Atributo</dt>
        <dd>Modificador del efecto de la etiqueta.</dd>
        <dt>Etiqueta</dt>
        <dd>Elemento que marca el inicio y fin de un efecto sobre los caracteres incluidos.</dd>

    </dl>
</div>
```

## Referencias documentales

* [W3 Schools](https://www.w3schools.com/html/default.asp) Cursos guiados y gratuitos.