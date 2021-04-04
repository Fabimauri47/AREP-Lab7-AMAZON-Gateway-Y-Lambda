# Lab #7 Taller Amazon Gateway y Lambda


## Introducción Del Proyecto

En este laboratorio 7, se creará un servicio web mediante la herramienta de Spark, la cual permite convertir de grados Fahrenheit a grados Celsius, haciendo uso de JSON. Luego hacemos uso de una maquina virtual AWS de EC2, para desplegar el servicio y publicándolo en el mismo. A partir de lo realizado anteriormente procedemos a crear un API Gateway para poder acceder al servicio y luego una aplicación web que use el servicio de Gateway. La integración no se realizo con un servicio Lambda, si no con un API. Además, se creó una aplicación desplegada en S3, la cual permitió que estuviera disponible el servicio web en cualquier máquina, con solo tener acceso a internet. La aplicación web permite al usuario ingresar el valor en Fahrenheit, para que luego el mismo API, le devuelva el valor correspondiente en Celsius.  


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

La arquitectura de este proyecto se baso en el siguiente modelo de clases:

  ![texto cualquiera por si no carga la imagen]()

La arquitectura de este laboratorio se basa en una clase llamada “ServicioSparkWeb” que es generada y cargada en un servidor con los puntos finales, la primera nos va a retornar un mensaje de “hola a todos” y la otra nos mostrara el valor de Celsius convertido en grados Fahrenheit. La clase de encargada de hacer uso del servicio de temperatura “clase ServicioTemperatura”, el cual tendrá una interface que nos proporcionará los servicios de temperatura. Esta clase es implementada por “SrvicioTemperaturaImpl” con una especifica implementación de servicios de temperatura, lo cual permitirá que el servicio sea más fácil de usar y que se pueda usar otra implantación de estos servicios. 


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
