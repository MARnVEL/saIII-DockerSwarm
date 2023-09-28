
# Docker Compose (servers + balancer)
>
> This repo was created to address some practical questions about Docker Compose posed by the class 'Upgrade Seminar III' of the **Formosa Polytechnic Institute** .
> *Este repositorio fue creado para abordar algunas preguntas prácticas sobre Docker Compose planteadas por la clase 'Seminario de Actualización III' del **Instituto Politécnico Formosa***.

## Tecnologías utilizadas

<div align="center" style="display: flex; justify-content: center; align-items: center;">
      <span style="margin-right: 20px;">
         <a href="https://es.javascript.info/" target="_blank">
               <img width="100" title='JavaScript' src='https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png'>
         </a>
      </span>
      <span style="margin-right: 20px;">
         <a href="https://www.docker.com/" target="_blank" title='Docker'>
               <img width="100" title='Docker' src='https://upload.wikimedia.org/wikipedia/en/thumb/f/f4/Docker_logo.svg/1920px-Docker_logo.svg.png'>
         </a>
      </span>
      </br>
</div>

# Introducción

> Este proyecto se trata de la "orquestación" de distintos contenedores con Docker Swarm.
> *Son simples servidores hechos con **JavaScript*** y **NodeJS**.
> Cada servidor se ejecuta en un contenedor independiente.
> Los contenedores que alojan los servidores se crean a partir de imágenes de **node:18-alpine**. Luego en estos contenedores hacemos las instalaciones correspondientes (a través de los Dockerfile's) para poder ejecutar servidores desarrollados con **NodeJS**.
> El balanceo de los contenedores se realiza a partir de **Docker Swarm**.

# Características

**SO: Windows 10**.

# Requerimientos

* Tener instalado **Dokcer Desktop**
* Tener instalado **Git**

# Usos

> Para utilizar este proyecto,  abrimos un CLI y nos dirigimos al directorio del sistema donde deseamos guardarlo. Ejecutamos el siguiente comando

```bash
git clone https://github.com/MARnVEL/saIII-DockerSwarm.git
```

* Iniciar la aplicación Docker Desktop

* En un CLI **inicializamos docker swarm**:

```bash
docker swarm init
```

* En el directorio de nuestro sistema donde guardamos el proyecto, ejecutamos en el CLI:

```bash
docker stack deploy -c node-services.yml myNodeJS
```

* Podemos listar los servicios de **swarm**:

```bash
docker service ls
```

* Ahora, debemos hacer unas pequeñas modificaciones de nuestros servidores dentro de los servicios desplegados para que podamos distinguir claramente el balanceo y/o funcionamiento de la herramiente "Docker swarm".

* Listamos los contenedores levantados y anotamos los IDs para los 3 servicios desplegados:

```bash
docker ps -a
```

* Para cada contenedor hacemos lo siguiente:

```bahs
docker exec -it <idContenedor> bash
```

* Hacemos una consulta `ls` para saber qué tenemos efectivamente dentro del contenedor.
* Una vez dentro del cotenedor hacemos:

  ```bash
  apg-get update
  ```

* Hacemos la instalación del editor nano para poder editar nuestro fichero `index.js`

  ```bash
  apg-get install nano
  ```
* Ahora editamos nuestro fichero `index.js`