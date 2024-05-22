FROM ubuntu:latest
EXPOSE 80 3000
#Instalar los programas base
RUN apt-get update
RUN apt-get install -y nodejs npm vim nginx
RUN npm install -g @angular/cli

COPY nginx.conf /etc/nginx/
RUN mkdir /volumen
RUN --mount=type=bind,source=./volumen,target=/volumen,readwrite
RUN cd /volumen && \
        ng new pagina && \
        echo "<h1>¡Bienvenido a mi servidor Docker con Angular!</h1> \n <router-outlet />" > pagina/src/app/app.component.html && \
        cd pagina && \
        ng build
#VOLUME [ "/volumen" ]
CMD ["sh", "-c", "nginx -g 'daemon off;'"]
