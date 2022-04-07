# Ejercicio 2
#### 1.- Creamos la red tipo bridge (red por defecto).

```
docker network create redbd
```
![Captura creacion red](Imagenes/red01.png)

#### 2.- Creamos la db con la red redbd y el volumen persistente (aunque la imagen crea uno por defecto).

```
docker run -d --name bbdd \
-e MARIADB_ROOT_PASSWORD=root \
-e MARIADB_DATABASE=prueba \
--network redbd \
-p 3306:3306 \
-v volumen_persistente:/backup \
mariadb
```
![Captura arranque contenedor db](Imagenes/red02.png)

#### 2.- Creamos el contenedor adminer para conectar a la bbdd.

```
docker run -p 8080:8080 --network redbd -d --name web adminer
```
![Captura arranque contenedor adminer](Imagenes/red03.png)