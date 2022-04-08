# Ejercicio 4
## Dockerfile
#### 1.- Creamos el contexto con un Dockerfile y una carpeta con la web de ejemplo.

![Captura contexto y dockerfile](Imagenes/dockerfile01.png)

#### 2.- Construimos la imagen.

```
docker build -t alvaropr/ejercicio4daw:v1 .
```

![Captura construccion](Imagenes/dockerfile02.png)

#### 3.- Lanzamos el contenedor.

```
docker run -d -p 80:80 --name ejercicio4 alvaropr/ejercicio4daw:v1
```

![Captura arranque del contenedor](Imagenes/dockerfile03.png)


#### 4.- Comprobamos en el navegador.

![Captura navegador](Imagenes/dockerfile04.png)

#### 5.- En mi caso creo un repositorio en mi cuenta de DockerHub.

![Captura creacion repositorio 1](Imagenes/dockerfile05.png)
![Captura creacion repositorio 2](Imagenes/dockerfile06.png)

#### 6.- Pusheo la imagen.

```
docker push alvaropr/ejercicio4daw:v1
```

![Captura push](Imagenes/dockerfile07.png)

#### 7.- Comprobamos que esta en DockerHub y que si la borramos en local, luego se descarga perfectamente.

![Captura tag en dockerhub](Imagenes/dockerfile08.png)

```
docker stop ejercicio4
docker rm ejercicio4
docker rmi alvaropr/ejercicio4daw:v1
docker pull alvaropr/ejercicio4daw:v1
```

![Captura descarga de imagen](Imagenes/dockerfile09.png)
