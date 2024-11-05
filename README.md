# P5-DNS
**Configura un contenedor coa imaxe oficial de bind9 usando docker-compose**

Para crear o contenedor, primeiro entrei nunha carpeta chamada 'composetest' e creei os arquivos necesarios. O importante o arquivo docker-compose.yml, onde poñemos o seguinte:

```
version: '3'

services:
  bind9:
    image: internetsystemsconsortium/bind9:9.18
    container_name: bind9-serveralex
    ports:
      - "54:53/tcp"
      - "54:53/udp"
    restart: unless-stopped
``` 

O apartado version indica a version do docker compose, neste caso a versión 3, services defina o servicio que emprego, neste  caso bind9, onde dentro del poñemos o seguinte: a imaxe de bind9; xunto o nome do contenedor; os portos que empreguei(na miña maquina non me deixaba a 53), neste caso os portos 54 para consultas; e nesta practica non empreguei volumes.

Unha vez configurado todos os arquivos, temos que empregar o comando `docker compose up`, onde aparecera o seguinte

```
[+] Running 1/0
 ✔ Container bind9-server  Recreated                                                                                           0.1s 
Attaching to bind9-server
bind9-server exited with code 1
```

Ahora comprobaremos, empregando o comando `dig @direccion_ip`, onde poremos a nosa ip .
