--- 
title: Moodle
summary: Herramienta para diseñar espacios web para organizar actividades de formación
authors: 
    - Jose Robledano
date: 2023-12-07
---
# Aplicación Web para gestionar entornos de aprendizaje on-line

**Moodle** ofrece una plataforma estable y gratuita para desplegar un entorno de aprendizaje propio.

Existe una activa comunidad, que se encarga de generar componentes y posibilidades para integrar otras tecnologías.

!!! info "Web oficial"

    En la [web oficial de Moodle](https://moodle.org/?lang=es) es posible descargar la versión más interesante para nuestro sistema.

## Requisitos de instalación

Para que funcione el sistema **Moodle**, es necesario una serie de servicios que permitan una infreestructura de soporte.

Hay varias posibilidades:
- Utilizar **docker**, para instalar los microservicios necesarios.
- Crear un **servidor web**, con PHP y una base de datos (Mariadb, MySQL).
- Preparar **MoodleBox** con un dispositivo Raspberry Pi.

### Docker

Es posible utilizar docker mediante comandos, o con la configuración de **docker-compose**. El primer paso es localizar un contenedor adecuado de la imagen de Moodle. 

!!! info "Docker Hub"

    Existen muchos contenedores publicados por los usuarios en el [docker hub](https://hub.docker.com/), sin embargo **no todos ellos son funcionales**, hay que poner atención en los comentarios y *pulls* realizados por la comunidad.


### Servidor Web

Necesita de varios servicios clave:

- **Servidor Web**, es necesario un sistema que permita este servicio. Puede estar proporcionado por un servidor de Internet, o en un sistema local. Servidores como **Apache** o **Ngix** son los más habituales.
- Interprete **PHP** que permita generar el código *HTML* para cada página.
- Base de datos **MySQL** o similar.


### MoodleBox

Una opción sencilla y fácil si se dispone del hardware adecuado, una Raspberry Pi 3 o superior. Actual como punto de acceso WiFi, y si hay posibilidad de conexión ethernet, también ofrece la posibilidad de actuar como enrutador, dándo acceso a otras redes.

!!! info "Bugs y credenciales"

    Es importante verificar y corregir posibles bugs que limiten la funcionalidad de este sistema. 
    
    Se ha localizado un problema en la versión rp3, que necesita especificar el tipo de encriptación para la conexión WiFi.

    También conviene tener presente los datos de configuración y acceso establecidos por defecto.


## Opciones iniciales

Una vez sea posible el acceso a la plataforma, se accede como usuario con el rol **Administrador** que dispone de todos los permisos de configuración.

### Cambiar el idioma

Desde la pantalla de configuración, se pueden añadir **paquetes de idioma** de las lenguas que se quieran utilizar en la plataforma. 

Existe una larga lista de idiomas posibles con una traducción completa de todo el sitio.

Una vez instalados los paquetes de idioma, se puede establecer por defecto cualquiera de ellos.

Cada usuario, puede tener su idioma por defecto. Así mismo, es posible cambiar el idioma pulsando sobre el icono del perfil de usuario *(en la parte superior derecha)* y seleccionando el lenguaje deseado entre los disponibles.


### Información del sitio

El administador puede establecer el **nombre del sitio**, y establecer la apariencia del mismo, editando la **página principal** cambiando el contenido que muestra.

También es posible establecer los elementos (cursos, noticias, publicidad, categorías...)


### Creación de usuario

Es interesante tener usuarios para gestionar desde los diferentes roles todas las operaciones habituales en la gestión de este tipo de plataformas.

Los usuarios se pueden crear de manera **manual** o de manera **automática** importando un fichero *csv* con una serie de campos concretos.


El formato del fichero CSV, requiere como mínimo, las columnas:

- username
- firstname
- lastname
- password 

!!! question "Formato CSV"

    El formato **CSV** se basa en un fichero de texto separando los datos con comas.
    
    Los datos correspondientes a un mismo elemento se escriben en la misma línea (*sin salto de línea*), separados por el caracter establecido como separador.

    Es importante establecer el **caracter separador** que puede ser: el *punto y coma*, la *coma*, el *tabulador*, o también es posible establecer un tamaño fijo para cada dato.

    Hay que tener presente que en los formatos numéricos, según la configuración regional o del lenguaje de programación utilizado, es posible que la interpretación de la parte decimal y el separador de miles puede generar confusión.

El usuario con el rol de **Administrador** puede establecer roles del sistema a otros usuarios. Los roles del sistema son el **Administrador** y el **Gestor**.

!!! info "**Cohortes**"

    Los cohortes permiten organizar usuarios para realizar acciones masivas.


### Categorías

Es posible establecer una estructura de categorías y subcategorías, para organizar los cursos y facilitar la distribución de estos.





