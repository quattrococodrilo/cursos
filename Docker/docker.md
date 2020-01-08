# Curso de Docker

## Instalar en Ubuntu

Para instalar docker ir a:
https://docs.docker.com/install/linux/docker-ce/ubuntu/

## Comandos

**docker ps -a**
*Muestra todos los procesos.
*Status EXITED nos dice que el contenedor está apagado

**docker inspect id/nombre_contenedor**
*Muestra la meta data del contenedor.
*El resultado es un json
*Filtro:
<code>
$ docker inspect -f '{{json .Config.Env}}' id/nombre_contenedor
  <br/>
$ ["PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"]
</code>



