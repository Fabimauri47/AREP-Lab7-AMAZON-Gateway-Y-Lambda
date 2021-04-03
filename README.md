# Lab #7 Taller Amazon Gateway y Lambda


## Introducción Del Proyecto

En este laboratorio 6 se realizó la construcción de un aplicativo web, diseñado en java y haciendo uso del framework Spark, con el fin de poder implementar y hacer uso de los certificados de SSL y así como de los protocolos HTTPS. La arquitectura se basa en dos nodos, que se comunican por medio de certificados (SSL), así como de hacer uso de una calculadora que se encarga de enviar la media y desviación estándar acorde a los valores suministrados anteriormente. Así como un control de nodos que se encargaran de llevar un control sobre las sesiones que se inician de diferentes usuarios y poder encriptar las contraseñas de estos mismos.


### Pre-Requisitos

- Para la realización de este laboratorio es necesario el uso de los aplicativos mencionados abajo de la descripción, en donde si no cuenta con alguno de estos,
       solo es necesario darle clic al que necesite y lo dirigirá a la página de instalación:


    * [Java 8](https://www.java.com/es/) - Codificación
    * [Maven](https://maven.apache.org/) - Manejo de Dependencias
    * [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git) - Control de Sistemas de veriones.
    * [Docker Install](https://docs.docker.com/engine/install/) - Despligue de proyecto.
    

### AWS Virtual Machine: Video de despliegue

>[![AWS Virtual Machine](amazon/amzn2-ami-hvm-2.0.20210318.0-x86_64-gp2)


### Integracion Continua con Circle CI
>[![CircleCI](https://circleci.com/gh/The-Developers-Eci/2020-2-PROYCVDS-THE_DEVELOPERS_ECI.svg?style=svg)](https://app.circleci.com/pipelines/github/Fabimauri47/-AREP-Lab3-CLIENTES-Y-SERVICIOS)
>

## Arquitectura 

La arquitectura de este proyecto se baso en el siguiente modelo, proporcionado en la el taller:

  ![texto cualquiera por si no carga la imagen](https://github.com/Fabimauri47/-AREP-Lab6-AP-DISTRIBUIDA-SEGURA/blob/main/Img/arquitectura%20Lab.png)

Para ello es necesario que dicha arquitectura cumpla algunos requerimientos como lo son el acceso al browser de la aplicación, permitiendo la autenticación, autorización e integridad de los usuarios. Además de tener al menos dos computadores comunicándose entre ellos y un acceso de servicios remotos que deben garantizar, autenticación y autorización entre todos los servicios.

La arquitectura de este laboratorio se basa en realización de un aplicativo web, haciendo uso de certificados web, en el cual permitirá acceder de manera local y remota sobre el control de los servicios que se están manejando en el aplicativo y así como consumirlos. También permitir la función de poder guardas los servicios que no se quieren que sean expuestos, como los de visualizar en el diagrama de arquitectura, haciendo uso de "KeyStore" y "TrustStore" en el aplicativo web manejado.

Los certificados se encontrarán almacenados en el directorio del repositorio y los dos TrustStore de los servicios que se ofrecen, para hacer uso de estos en los aplicativos. Para poder agregar un nuevo servicio, se deben crear "KeyStore" y "TrutStore" nuevos para cada servicio que se va a manejar y agregar dichos certificados a cada uno de los servicios que se van a usar. Por último, como segundo nivel de seguridad se debe contar con un servicio de LOGIN, el cual establecerá el bloqueo del servicios, cuando la sesiones se encuentren inactivas, además de cifrar las contraseñas de los usuarios haciendo uso de la Funciones HASH.


### Guia de Instalación

1. Primero se debe clonar el repositorio, con el siguiente comando descrito:

       git clone https://github.com/Fabimauri47/-AREP-Lab6-AP-DISTRIBUIDA-SEGURA
    

2. Luego proceda abrir el cmd (Ventana de comandos) en donde tiene el repositorio alojado y ejecute el siguiente comando:

       mvn package
    

3. Ejecutamos el programa de manera local,dentro del directorio DOCKERFILES con el siguiente comando:

       docker-compose up -d
   

4. Para verificar que todo que la ejecución del programa se hizo de manera correcta, ingresamos el siguiente comando:

       docker ps
   
5. Para hacer ingreso del aplicativo de manera web, de forma local se ingregar la siguiente URL:

        https://localhost:8000/
		
6. Para crear la documentación JavaDoc y que se genera apartir de lo realizado, se ejecuta el siguiente comando:

		mvn javadoc:javadoc

## Corriendo Pruebas

Para correr las pruebas, usamos el siguiente comando en una terminal CMD o en una terminal GIT:

         mvn test


## Construido con

* [Java](https://www.java.com/es/) - Codificación y Lenguaje de Programacíon.
* [Maven](https://maven.apache.org/) - Manejo de Dependencias.
* [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/) - Programa usado para la Codificacíon.
* [AWS](https://aws.amazon.com/es/education/awseducate/) - Despligue de Ambiente Web
* [Docker](https://www.docker.com/) - Control y despliegue del proyecto
* [Spark](http://sparkjava.com/) - Microframework Para aplicaciones en JAVA 8


## Autor

* **Fabián Mauricio Ramirez Pinto** [Fabimauri47](https://github.com/Fabimauri47)


## Licencia

Este proyecto cuenta con la licencia GNU: General Public License - see the [LICENSE.md](https://github.com/Fabimauri47/AREP-Lab1-Calculadora/blob/main/LICENSE.txt) 
