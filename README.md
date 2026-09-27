# Web contador cuenta regresiva GTA6
Este proyecto es sencillo, un poco de HTML5, JS y CSS3.
Combinado con Docker para exponerlo a internet en un contenedor.


## ¿Qué necesitas?
* Un dominio y el panel de acceso al dominio.
* Registrar el subominio al que quieras asignar el proyecto web.
* Una máquina conectada a internet con una IP pública o usar algo como Cloudflare Tunnel.
* Apuntar el subodminio a la IP pública de la máquina.
* Tener instalado en la máquina Docker.
* Un contenedor con Traefik para que haga de proxy inverso y configurarlo para que cree y firme con certificados de Let's Encrypt.
* Una red docker para que Traefik vea el contenedor del proyecto y pueda conectar a los clientes con el servidor web.

## ¿Cómo lo configuro?
Fácil, tan fácil como:
* Cambiar el nombre del ficheor .env.example por .env
    * Desde la carpeta del proyecto puedes hacer `mv .env.example .env`
* Cambiar el contenido de la variable DOMINIO que está dentro del fichero .env

# ¡Eso es todo!
Lo único que falta es levantar y dejar expuesto el proyecto con el siguiente comando
`docker compose up -d`
Empezará a descargarse la imagen de nginx:alpine y luego se expondrá el proyecto web bajo el dominio indicado.
