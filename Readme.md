<div style="text-align: center;">

# DOCKER 2

</div>

<br>

<div style="text-align: center;">

## 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo

</div>

**`sudo docker pull httpd:2.4`**

Con este comando descargamos la imagen de Apache con el tag 2.4.

**`sudo docker run httpd:2.4`**

Con este comando iniciamos la imagen de Apache con el tag 2.4.

**`sudo docker ps -a`**

Con este comando comprobamos que el contenedor está creado.

<br>

<div style="text-align: center;">

## 2. Crea un contenedor con el nombre 'dam_web1'

</div>

**`sudo docker run --name dam_web1 httpd:2.4`**

Con este comando creamos un contenedor con el nombre `dam_web1`.

**`sudo docker ps -a`**

Con este comando comprobamos que el contenedor está creado.

<br>

<div style="text-align: center;">

## 3. ¿Cómo acceder desde el navegador de tu equipo?

</div>

Utiliza **bind mount** para montar el directorio `htdocs` de Apache en un directorio que elijas.

Primero, detén el contenedor:

**`docker stop dam_web1`**

Este comando detiene el contenedor `dam_web1`.

Elimina el contenedor:

**`docker rm dam_web1`**

Este comando elimina el contenedor `dam_web1`.

Ahora, crea un nuevo contenedor con el puerto mapeado y el bind mount:

**`docker run -d --name dam_web1 -p 8080:80 -v /home/accesodatos/SXE/Html:/usr/local/apache2/htdocs httpd:2.4`**

Este comando crea un contenedor `dam_web1` con el puerto 8080 mapeado al puerto 80 del contenedor, y el directorio `/home/accesodatos/SXE/Html` mapeado a `/usr/local/apache2/htdocs` en el contenedor.

<br>

<div style="text-align: center;">
