# Ejercicio 2
#### 1.- Arrancamos los contenedores con los parámetros especificados en la tarea

```
docker run --name c1 -p 8181:80 --mount type=bind,source=/c/Users/alvar/Documents/Estudios/Otros/Tarea\ Git\ y\ Docker/tareas-docker/Ejercicio\ 2/saludo,destination=/var/www/html -d  php:7.4-apache
docker run --name c2 -p 8282:80 --mount type=bind,source=/c/Users/alvar/Documents/Estudios/Otros/Tarea\ Git\ y\ Docker/tareas-docker/Ejercicio\ 2/saludo,destination=/var/www/html -d  php:7.4-apache
```
![Captura arranque contenedor](Imagenes/mount01.png)

#### 2.- Comprobamos que se resuelven a traves del navegador.

![Captura contenedor](Imagenes/mount02.png)

