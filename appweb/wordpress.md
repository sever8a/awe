--- 
title: WordPress
summary: Gestor de contenido desplegado en AWS
authors: 
    - Jose Robledano
date: 2024-01-25
---

# WordPress

Un gestor de contenido que ofrece mucho por poco.

# Puesta en marcha con una infraestructura AWS

Disponiendo del acceso a AWS academy, se puede utilizar un curso Learner Lab. Con este tipo de curso es posible desplegar una infraestructura para disponer de WordPress en la nube.

Hay ciertas limitaciones, como el tiempo de activación continua del laboratorio (se desactiva a las 4 horas), o el límite de créditos educativos.

 
## Pasos previos 

 

Accede a tu cuenta estudiante de AWS, y conectate al curso Learner Lab. 

 

Localiza en el apartado **contenido** la opción **iniciar el laboratorio**. 

 

Una vez se haya cargado el Laboratorio, aparecen unos botones en la parte superior. Pulsa “start lab” para que se inicie. Recuerda que cada inicio tiene una duración de 4 horas. Una vez concluido este tiempo podrás volver a iniciar el laboratorio. 

 

## Crear la máquina virtual 

En este ejemplo se ilustra con una máquina virtual utilizando el sistema operativo Linux Amazon 2023 (de la capa gratuita), con las opciones por defecto de procesamiento y computación. 

Como la idea es disponer de un servicio http al que sea posible acceder de manera remota, es aconsejable crear un Registro de Seguridad estableciendo que sea posible el acceso desde cualquier IP a la máquina.

Otra cuestión importante es la IP de instalación en el servidor. 

Por defecto, AWS asigna una dirección IP pública dinámica (gratuita), pero al realiar la instalación de WordPress se almacena la dirección utilizada para referenciar las páginas y hojas de estilo utilizadas. 

Esto es un problema cuando la IP pública cambia, algunos recursos de la aplicación web dejan de estar disponibles.




## Accede al servicio EC2. 

Antes de comenzar con la instancia.
Como el objetivo es montar un servicio WordPress, es necesario habilitar el acceso **http** público para poder acceder a la configuración y gestión de la aplicación web. 

Esto se puede realizar utilizando las opciones por defecto, durante la creación de la máquina virtual, o seleccionando el apartado **Registros de seguridad** y creando una propia.

Si se hace de esta manera, hay que permitir el acceso externo desde cualquier IP a los puertos SSH y HTTP (cómo mínimo).

!!! info "Registro de seguridad"

    Consiste en determinar las reglas del cortafuego de acceso a la máquina. Hay que crear las reglas necesarias seleccionando el **servicio/puerto** y quíen podrá acceder.

    En este caso debería ser el puerto/servicio **HTPP** y añadir que se accesible desde cualquier IP **0.0.0.0/0**


**Lanza una nueva instancia**, si no tienes alguna preparada. 

Asigna un **nombre reconocible** a la instancia.  

Selecciona el sistema operativo **Linux Amazon**. 

Establece las **credenciales de acceso *Vockey***. 


## Dirección IP fija 

Hay que tener en cuenta que AWS asigna una dirección IP pública dinámica cada vez que iniciamos la instancia. Esta situación no funciona bien con WordPress, ya que al volver la ejecución de la instancia tendrá una IP diferente a la utilizada en la configuración. 

Esto genera que no funciona bien la resolución de las paǵinas web de WordPress, dando problemas en el acceso a las páginas y a los estilos. 

La solución es disponer de una dirección IP fija. En AWS se llaman Elastic IP. 

La instalación puede verse perjudicada, si cambia la dirección IP pública de configuración. La solución más sencilla es conseguir una dirección IP Elástica (así las llama AWS cuando son IP fijas).  

En el menú lateral localiza la opción IP elástica. Crea una nueva dirección IP y asignala a la instancia de la máquina virtual. 

De esta forma siempre que se ponga en marcha la máquina será la misma dirección IP pública.

!!! alert "Importante"

    Si no realizas esta asignación **antes de realizar la instalación de WordPress**, la aplicación dejará de estar accesible cuando vuelva a tener asignada una dirección IP pública diferente.

## Instalación Docker en máquina AWS Linux 2023 

**Conecta** con la máquina virtual, para tener acceso desde un terminal (por ejemplo con ssh). 

 
### Instalar docker 

1- Actualizar la caché de los paquetes 

``` bash
    sudo yum update -y 
```

2- Instalar la versión community más reciente de docker 

``` bash
    sudo yum install -y docker 
```

3- Iniciar el servicio Docker 

``` bash
    sudo service docker start 
```

4- Agregar al usuario ec2-user al grupo docker 

``` bash
    sudo usermod -a -G docker ec2-user 
```

Importante!! Hay que cerrar sesión con el usuario ec2-user (exit) y volver a conectar para que el usuario actualice los permisos, que se han cambiado. 

5- Para que docker comience cada vez que se inicie la máquina 

``` bash
    sudo chkconfig docker on 
```  

6- Comprobar que funciona docker sin utilizar sudo. 

``` bash
    docker ps 
```


### Instalar docker-compose 

 

1- Instalar la última versión de Docker-compose 

``` bash
    sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose 
```


2- Arreglar los permisos, después de la descarga 

``` bash
    sudo chmod +x /usr/local/bin/docker-compose 
``` 

3- Comprobar funcionamiento 

``` bash
    docker-compose version
```
 

## WordPress en la máquina virtual 

Lo más sencillo es utilizar docker-compose, ya que para la instalación de Wordpress será necesario utilizar una imagen docker para el servidor web (que utilizará el servicio http por el puerto 80) y una base de datos (que conectará con el contenedor del servidor web). 

 

Es recomendable que la redirección del puerto 80 sea al puerto 80 (en lugar del 8080 u otro que pueda aparecer en el fichero .yml). 

``` bash title="Ejemplo de fichero docker-file.yml"

version: '3.1'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 80:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - wordpress:/var/www/html

  db:
    image: mysql:8.0
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:
  db:
```
 

El primer paso es crear el fichero .yml en la instancia.

- Crea un nuevo directorio.
- Dentro de este crea el fichero *tu-nombre.yml*.
- Abre el fichero con un editor. Por ejemplo *nano*. ```nano tu-nombre.yml```
- Pega el contenido que encuentres en las instrucciones del docker-hub, o el ejemplo anterior. 

Se puede hacer de otras formas diferentes. 

 
### Lanzar WordPress
Desde una consola conectada a la instacia de la máquina, hay que realizar la llamada a *docker-compose* para que descargue e inicie los contenedores según las especificaciones del fichero yml.

Un ejemplo de comando podría ser el siguiente: 

``` bash
    cd  ~/wp/ && docker-compose -f docker-compose.yml up -d 
```


En la primera parte de esta instrucción, nos situamos en el directorio wp que se debe haber creado en el directorio home del usuario. En la segunda parte se lanza docker-compose utilizando un fichero yml llamado docker-compose, y se utiliza la opción -d para que el proceso esté en segundo plano. 

Hay que lanzar el servicio desde una terminal conectada a la máquina virtual. 

 

Ten presente que tarda un poco en instalarse el contenedor docker e iniciarse (sobretodo la primera vez). 

 

## Acceso a WordPress 

Recuerda que se puede acceder utilizando la IP pública o el nombre DNS publico que tiene establecida la máquina. 

 

Esta información está disponible en la pantalla “Instancias”, pulsando sobre la instancia que estamos utilizando. 

En los detalles aparece la información de la IP y DNS público. 

Verifica si es necesario cambiar el puerto. 

 

Accede con tu navegador favorito. 

 

