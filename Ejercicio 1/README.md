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

![Captura contenedor](Imagenes/01.png)

#### 3.- Copiamos el contenido web a /var/www/html

```
docker cp web/. web:/var/www/html
```

#### 4.- Comprobamos que se ha subido el contenido a la máquina

![Captura contenedor](Imagenes/02.png)

