# Curso de Docker

## Instalar en Ubuntu

Para instalar docker ir a:
<https://docs.docker.com/install/linux/docker-ce/ubuntu/>

## Comandos

**docker run**

-   Genera un contenedor nuevo.
-   \--detach/-d: Correr Docker en segundo plano
    \--  docker run -d --name server -p 8080:80 nginx
    \--  docker run -d --name db mongo
    \--  docker run -d --name db -v path_local:path_contenedor imagen
    \--  docker run -d --name db --mout src=nombre_volumne,dst=path_contenedor

**docker ps -a**

-   Muestra todos los procesos.
-   Status EXITED nos dice que el contenedor está apagado
-   docker ps -q
    \--  Lista id de containers.

**docker inspect id/nombre_contenedor**

-   Muestra la meta data del contenedor.
-   El resultado es un **json**
-   Filtro:


    $ docker inspect -f '{{json .Config.Env}}' id/nombre_contenedor
    $ ["PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"]

**docker rename nombre_contenedor nuevo_nombre**

-   Renombrar contenedor
-   Los nombres no se pueden repetir
-   docker run --rename nuevo_nombre nombre_contenedor
    \--  Genera un contenedor nuevo que comparte la imagen con el contenedor anterior.

**docker log nombre_contenedor**

-   Crea un contenedor nuevo.

**docker log nombre_contenedor**

-   Muestra los outputs de los contenedores.

**docker rm nombre_contenedor**

-   Elimina el contenedor.
-   Eliminar todos los contenedores.
-   rm -f: fuerza la eliminación del contenedor.

    $ docker rm $(docker ps -aq)

## Ubuntu en contenedor

**docker run -it ubuntu**

-   Corre la terminal de Ubuntu contenido.
    \--  Comprobar con: cat /etc/lsb-release
-   **docker run -it ubuntu comando**: ejecuta un comando

**docker exec -it nombre_contenedor comando**

-   Ejecuta un comando en un contenedor que ya está corriendo.
    \--  ps -fea: procesos de todas las sesiones.

**Ciclo de vida**: cuando el _rut command_ finalice, el contenedor también finaliza.

**docker kill nombre_contenedor**

-   Mata el proceso de un contenedor

## Docker vulumes

En Linux se encuentran en **/var/lib/docker/volumes**

**docker volume**

-   _ls_: muestra los volumenes.
-   _prune_: elimina los volumenes que no están en uso.
-   _create_ nombre: crea un nuevo volumen
-   docker run -d --name db --mout src=nombre_volumne,dst=path_contenedor

## Imágenes

**docker pull**
-   Descarga una imagen.
