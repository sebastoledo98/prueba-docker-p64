# Prueba de Docker Sistemas Distribuidos Periodo 64

## Instrucciones para correr la imagen docker

Primero corremos el comando

    docker build -t prueba-docker .

Una vez que se termine de construir corremos el comando


    docker run --name prueba-docker -p 3000:80 prueba-docker

Probamos que corra todo accediendo a la direccion `localhost:3000`, esto debe mostrarnos nuestra pagina de bienvenida con el mensaje
