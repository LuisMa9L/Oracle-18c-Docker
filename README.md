# Oracle 18c XE en Docker

#### Clonar el repositorio de oracle/docker-images

    git clone https://github.com/oracle/docker-images.git

#### Para crear una imagen de Linux oracle con Oracle 18c XE, ejecutar el archivo buildDockerImage.sh que se encuentra en el directorio `docker-images/OracleDatabase/SingleInstance/dockerfiles/`
La contrucción de la imagen tarda bastante tiempo ya que primero descarga los binarios de la instalación con las dependencias necesarias y luego contruye la imagen 

``` sh
./buildDockerImage.sh -v 19.3.0 -e
```
Solo funciona con la versión 18c XE, para las demás versiones se debe descargar el respectivo binario de la instalación 
* Si hay algún problema probar volver a ejecutar el script
#### Para crear el contenedor
``` sh
docker run --name ora \
-p 1521:1521 -p 5500:5500 \
-e ORACLE_PWD=1234 \
-v /Users/lmml/datos_oracle:/opt/oracle/oradata \
oracle/database:18.4.0-xe
```
Para más detalles ir a [README.md](https://github.com/oracle/docker-images/blob/master/OracleDatabase/SingleInstance/README.md) de docker-images

#### Para conectar a *SQLDeveloper* 

* Usuario: **SYSTEM** 
* Contraseña: **1234** 
* Puerto: **1521** 
* SID: **XE**
