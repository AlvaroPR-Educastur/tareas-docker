# Ejercicio 1
## Web
#### 1.- Arrancamos el contenedor de apache con php

```
docker run --name web -p 8000:80 -d  php:7.4-apache
```

#### 2.- Comprobamos que se levanta el contenedor.

```
docker ps
```

![Captura contenedor](Imagenes/web01.png)

#### 3.- Copiamos el contenido web a /var/www/html

```
docker cp web/. web:/var/www/html
```

#### 4.- Comprobamos que se ha subido el contenido a la máquina

![Captura contenedor](Imagenes/web02.png)
![Captura browser](Imagenes/web03.png)
![Captura browser](Imagenes/web04.png)
![Captura browser](Imagenes/web05.png)


## Database
#### 1.- Arrancamos el contenedor de mariadb con sus variables de entorno.

```
docker run --name bbdd \
-e MARIADB_ROOT_PASSWORD=root \
-e MARIADB_DATABASE=prueba \
-e MARIADB_USER=invitado \
-e MARIADB_PASSWORD=invitado \
mariadb
```

![Captura despliegue mariadb](Imagenes/db01.png)

#### 2.- Comprobamos que se ha creado correctamente.

![Captura despliegue mariadb](Imagenes/db02.png)