# Curso de Docker

## Instalar en Ubuntu

Para instalar docker ir a:
<https://docs.docker.com/install/linux/docker-ce/ubuntu/>

## Comandos

<b>docker ps -a</b>

-   Muestra todos los procesos.
-   Status EXITED nos dice que el contenedor está apagado
-   docker ps -q
--  Lista id de containers.

<b>docker inspect id/nombre_contenedor</b>

-   Muestra la meta data del contenedor.
-   El resultado es un **json**
-   Filtro:
```
$ docker inspect -f '{{json .Config.Env}}' id/nombre_contenedor
$ ["PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"]
```

<b>docker rename nombre_contenedor nuevo_nombre</b>
-   Renombrar contenedor
-   Los nombres no se pueden repetir
-   docker run --rename nuevo_nombre nombre_contenedor
--  Genera un contenedor nuevo que comparte la imagen con el contenedor anterior.

<b>docker run</b>
-   Crea un contenedor nuevo.

<b>docker log nombre_contenedor</b>
-   Muestra los outputs de los contenedores.

<b>docker rm nombre_contenedor</b>
-   Elimina el contenedor.
-   Eliminar todos los contenedores:
```
$ docker rm $(docker ps -aq)
```
