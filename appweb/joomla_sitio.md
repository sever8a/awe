# Pasos para montar un sitio Joomla

Pasos básicos para comenzar a crear un nuevo sitio utilizando Joomla.

Se presupone que ya se ha realizado la instalación, y ahora estamos diseñando un nuevo sitio web.

!!! info "Acceso"

    Recuerda que para acceder como administrador, debes acceder con la ruta *administrator*.

    **ruta_a_mi_joomla/administrator**

## Cambio de idioma

Desde la pantalla de Administrador, se accede al menú lateral **System**. 
En el apartado **Manage**, se puede seleccionar la opción **Languages**.

Se muestran la lista de los idiomas disponibles (instalados), tanto para el **sitio** web como para las páginas de **administrador**.

!!! qestion "Atención a los detalles"

    En la parte superior izquierda aparece un desplegable donde se puede seleccionar las opciones de idioma para el **Sitio** o para el **Administrador**.

Si el idioma que interesa no está en la lista *(por defecto aparece inglés GB)* habrá que instalar el nuevo idioma **Install languages**, que está en la parte superior izquierda.

Esta opción nos muestra el listado de idiomas disponibles. También es posible realizar búsquedas.

!!! info "La versión adecuada"

    Es importante que el paquete de idioma esté disponible para la versión de Joomla que se está utilizando. Si no, es posible que se generen algunos errores o aparezcan textos en idioma diferente.


Basta con pulsar el botón de instalación del idioma, y esperar que se complete.

Volviendo a la plantalla con la lista de idiomas instalados, se puede seleccionar el idioma deseado y establecerlo por defecto. Recuerda que se puede cambiar el idioma del sitio y del administrador de manera independiente.

!!! info "Idiomas"

    === "Idiomas" 
        
        Tener idiomas diferentes para el sitio y la zona del administrador, es importante porque puede ser de ayuda si seguimos un tutorial en otro idioma.


    === "Prueba la instalación"
    
        Para este ejemplo, se ha instalado los idiomas *español* y *frances*.

        Se ha establecido *español* como idioma por defecto para el administrador.



## La plantilla

Desde la opción **Sistema**, en el apartado **Plantillas**, se puede realizar la gestión de el estilo general; tanto del sitio web como de las pantallas del administrador.

Por defecto Joomla 4 tiene la plantilla del sitio: **Cassiopeia**. Y la plantilla de administrador **Atum**. Se puede comprobar al visualizar la lista de plantillas en ambos casos.

!!! question "Opciones disponibles"

    Es importante observar que se hace referencia a las **plantillas** y a los **estilos**. Siendo posible acceder a los listados correspondientes de cada uno de ellos, disponibles tanto para el *sitio* como para el *administrador*.

Con la opción **Sistema** y **Estilos de plantillas del sitio**, se accede a la lista de estilos disponibles. Por defecto solo estará el estilo Cassiopeia.

   * Pulsando sobre el nombre del estilo de la plantilla, se accede a la pantalla de configuración. Hay algunas opciones que se pueden configurar desde esta pantalla. 

!!! info "Personalización Cassiopeia"

    En Cassiopeia se puede cambiar el logo que aparece en la parte superior y el color.


## Los menús

Sirven para acceder al contenido del sitio web. 

Desde el panel de control del administrador, se puede acceder a los menús.

!!! info "Menús y sus opciones"

    Es importante conocer que los Menús del sitio hacen referencia a agrupaciones de **opciones** que llevan o muestran diferente contendio del sitio web.

    Las **opciones** de cada menú, actúan como enlace para cargar un contenido concreto.

Al acceder al **"Main Menu"** se observa la lista de opciones que tiene ese menú. En la parte superior izquierda, con el botón *Nuevo*, se puede crear una nueva opción dentro del menú. 


Al crear una opción del menú es obligatorio especificar el **elemento del menú**, es decir qué se mostrará cuando se pulse esta opción del menú. 

!!! question "Variacíon de opciones"

    Según el tipo de elemento seleccionado, cambiarán las opciones disponibles en el resto de pestañas de configuración.

# Un ejemplo concreto.

Vamos a crear una web para mostrar información del IES Severo Ochoa.

Nuestro sitio tendrá una página de incio y otra con los datos de contacto.

## Titulo del sitio

En la opcíon **Sistema** - **Configuración global** podemos poner el título de nuestro sitio, así como los metadatos y otras opciones para los buscadores. 

!!! info "SEO"
    
    Son las opciones para el posicionamiento en web. Los buscadores obtienen los datos del sitio web y los indexan para poder ser localizados.

En el apartado **Sistema** también se puede variar el tiempo de conexión a la base de datos, para aumentarlo a 60, al menos durante el trabajo de edición de contenido.

Ya es posible previsualizar nuestro sitio web, aunque de momento no está completo.

## Artículos

En este caso como vamos a necesitar dos páginas, crearemos dos artículos. Estos dos artículos serán *páginas estáticas*, así que también será necesario crear una categoría **página**.

!!! info "Creación de contenido"

    === "La categoria"
        Desde la opción **Categorias**, aparecen todas las que están definidas y se pueden crear nuevas.

        Colocamos de nombre *Página* y observamos que hay algunas opciones de configuración que se pueden aplicar a todos los elementos de esta categoría. 

        De momento lo dejamos por defecto.

    === "Los artículos"

        Desde la opción "Artítulos" creamos dos nuevos, asignando la catería anterior a ambos.

        Uno se llamaría **Inicio** y otro **Contacto**.

En cada artículo hay varias opciones para configurar algunas características:

* *Mostrar título* **Ocultar**.
* Ocultar todas las opciones (autor, visitas, etiquetas... )

En el apartado **Contenido**, en el artículo *Inicio*, escribimos la presentación del IES y en el artículo *Contacto*, algunos datos de contacto.


## Menú para acceder a las páginas

En la opción **Menú** - **Gestionar**, aparecen los menús disponibles.

Creamos una nuevo con el nombre *Principal*.

Añadimos dos elementos al menú. Se puede hacer pulsando en el icono *"Elementos del menú"*, o pulsando en el nombre del menú, en la parte izquierda.

Cada elemento tiene que tener un nombre y elegir *"Tipo de elemento del menú"*.

Y elegimos en la sección de **Artículos**, **Mostrar un solo artículo**.

!!! info "Página de inicio"

    Para la página de **Inicio** hay que establecer la propiedad *Página de inicio*.

    Aparecerá una casita junto al nombre del menú.

## Módulos

Los módulos son elementos preconstruidos que incorporamos al sitio web. Por ejemplo, los menús. 

También es posible añadir módulos específicos desde Internet.

!!! question "Asigna un módulo"

    El menú necesita un módulo (Elemento con posición) para poder mostrarse. En este caso será el **módulo Menú** y la posición podemos variarla  entre las posibilidades que ofrece los estilos de la plantilla.

Los módulos  Google map.

