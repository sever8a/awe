# Joomla

*Un viejo conocido que regresa con muchas opciones.*
CMS de propósito general que permite multiples configuraciones 

!!! info "Atención con la complejidad"
    *Cuidado con extraviarse con sus módulos*. La complejidad del diseño puede generar un autentico kaos. 

## Historia

Joomla es un CMS libre, que llegó a ser lider en implantación de sitios web. Se convirtió en el referente para otros desarrollos posteriores que, de alguna manera lograron superarle.

Surge como una aplicación web de propósito general, de manera que se puede utilizar para generar todo tipo de páginas web.

Sin embargo, la cantidad de opciones y la cada vez más complicada configuración de estas, provocó un aumento de la complejidad de su uso. 

Finalmente otros CMS, más sencilos de configurar, fueron ocupando su lugar.

Actualmente está en un proceso de regeneración.

!!!info "Su desarrollo actual"
    Las últimas versiones son la **4.4** y **5.0**

## Instalación

Como otros CMS, también necesita una base de datos para almacenzar los distintos objetos con los que generar la web. En este caso no sirve cualquier base de datos, es necesario que sea **PostgreSQL** o **MySQL**.

Es requisito un **servidor http** que interprete **lenguaje PHP**.

Se pueden instalar los recursos necesarios en un servidor, u otra posibilidad es utilizar un contenedor *Docker* para lanzar la aplicación. En este caso es necesario comprender que con esta configuración se utilizan dos contenedos:
- Uno para Joomla.
- Otro para la base de datos.

## Creación de contenido

¿Qué queremos conseguir?, ¿cómo será el sitio web que diseñamos? 

Teniendo claro el contenido y estructura que tendrá el sitio web; una opción es elegir e instalar una plantilla que se ajuste a lo que necesitamos.

Cada plantilla contiene elementos diferentes, ya prediseñados, lo que facilita mucho cualquier desarrollo.

!!! question "Personalización"

    También es posible realizar el diseño de estilo propio, directamente utilizando **HTML** y **CSS**.

    Ampliando las opciones de configuración de cualquier plantilla.


### Artículos

Son el **contenido básico**. 

Los artículos, pueden contener, a su vez, otros módulos o complementos con diferentes funcionalidades según la necesidad.

Se organizan en categorias y subcategorias. Esta estructura tiene que estar creada previamente.

!!! info "Categorías"
    
     Observa que la categoria no tiene porqué hacer referencia a la temática de cada artículo, sino más bien a la función de este en el diseño del sitio web.


### Menús

Los menús permiten acceder a diferentes artículos o componentes. 

Cada **menú** se compone de **items** que corresponden a las opciones del menú.

* Cada **item**, se vincula con un evento. Los eventos son acciones sobre el contenido del sitio web. Por ejemplo, mostrar la lista de categorías, mostrar un único artículo, mostrar contactos, ... 

El **menú** se deben ubicar en algún **módulo** de posición, de los que ofrece la plantilla de estilos utilizada. Utilizando la opción **Posición**.


### Extensiones

Hace referencia a cualquier tipo de elemeto añadido: pueden ser *plugin*, *complementos*, *módulos*, *plantillas*...

Se instalan desde la pantalla de administardor, utilizando la opción **Sistema**. 


!!! question "Activación de complementos"

    Cuando se instala alguna nueva extensión, es necesario que sea activada para poder utilizarla en el sitio web.









