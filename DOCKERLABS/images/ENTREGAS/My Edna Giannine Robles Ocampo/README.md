1.	Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

| Herramienta | Definición                                                 | Funcionalidad principal                                      | Casos de uso típicos                                                      |
|-------------|------------------------------------------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------|
| Docker / DockerLabs | Plataforma de virtualización ligera basada en contenedores | Ejecutar aplicaciones y entornos aislados de forma rápida     | Simulación de laboratorios, despliegue CI/CD, microservicios             |
| nmap        | Escáner de red y puertos                                    | Descubre hosts y servicios en una red                         | Auditorías de seguridad, mapeo de red, detección de servicios            |
| hydra       | Herramienta de fuerza bruta para autenticación              | Intenta contraseñas en múltiples protocolos                    | Auditoría de contraseñas, pentesting de servicios remotos                |
| file        | Comando para identificar tipo de archivo                    | Lee la cabecera y metadatos para clasificar archivos          | Forense digital, scripts de procesamiento de archivos                    |
| steghide    | Herramienta de esteganografía                               | Inserta o extrae datos ocultos en ficheros (imágenes, audio)  | CTF, ocultación de información, análisis forense                         |

2.	Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando. 3. Realice un diagrama de flujo de todo el procedimiento realizado.
2.1. Despliegue del laboratorio

![Descripción](imagen/RETO%20AMOR%20IMAGEN%201.jpg)

docker pull: descarga imagen de DockerHub.
raolab/networks:amor: repositorio e imagen.

  Variantes:
      docker pull alpine
      docker pull ubuntu:latest
      docker pull private/imagen:tag

![Descripción](imagen/RETO%20AMOR%20IMAGEN%202.jpg)

docker run: ejecuta un contenedor.
-it: interactivo con terminal.
--rm: elimina contenedor al salir.
/bin/bash: shell de arranque.

    Variantes:

      docker run -d --name miapp alpine
      docker run -p 8080:80 nginx
      docker run --volume /host:/container alpine
