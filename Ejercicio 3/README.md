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

#### 3.- Creamos el contenedor adminer para conectar a la bbdd.

```
docker run -p 8080:8080 --network redbd -d --name web adminer
```
![Captura arranque contenedor adminer](Imagenes/red03.png)

#### 4.- Nos conectamos a la bbdd via web.

![Captura conexion adminer](Imagenes/red04.png)

### Extra
#### Creamos una bbdd via web.

![Captura creacion db 1](Imagenes/red05.png)
![Captura creacion db 2](Imagenes/red06.png)

#### Consulta en modo texto a la bbdd desde la web.

![Captura consulta](Imagenes/red07.png)

#### Comprobacion de los recursos corriendo.

```
docker ps
docker volume ls
docker network ls
```

![Captura comprobacion](Imagenes/red08.png)

#### Eliminacion de todos los recursos

```
docker stop bbdd
docker stop web
docker rm web
docker rm bbdd
docker network prune
docker volume prune
```

![Captura comprobacion](Imagenes/red09.png)