# **<p align="center">:imp::rotating_light::skull:LABORATORIO AMOR - DOCKER LABS:skull::rotating_light::imp:</p>**
# **<p align="center">:warning: TALLER INDIVIDUAL. :warning:</p>**
# <p align="center">![DANIEL TORRES JARAMILLO](https://cdn.hashnode.com/res/hashnode/image/upload/v1721789878989/a33685bd-c727-4147-90b5-101ab06186a7.jpeg?w=1600&h=840&fit=crop&crop=entropy&auto=compress,format&format=webp)</p>

# <p align="center">DANIEL TORRES JARAMILLO
# <p align="center">:shipit::computer:**"LOVE" MACHINE**:computer::shipit: </p>

# <p align="LEFT">DESARROLLO

1.	Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.
# <p align="LEFT">TOOLS
![Cyber](https://media4.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3MmNhM2t4ODdvcno4amdxaHpsZ2QwNjR4MHFiOGhna2QzcWFnOXF1OCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/3oKIPqsXYcdjcBcXL2/giphy.webp)


   

|      Herramienta     |      Definición                                                                                                       |      Funcionalidad principal                                                                            |      Casos de uso comunes                                                                                                                      |
|----------------------|-----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|     DOCKER           |     Plataforma de virtualización ligera basada en contenedores.                                                       |     Desplegar, gestionar y aislar aplicaciones   en entornos autocontenidos llamados contenedores.      | Crear laboratorios de ciberseguridad. Aislar   entornos de desarrollo. Automatizar despliegues.                         |
|     NETDISCOVER      |     Herramienta de descubrimiento de red en capa 2 (ARP).                                                             |     Detectar dispositivos activos en una red   local sin necesidad de escaneo activo.                   | Identificar hosts en redes desconocidas. Reconocimiento pasivo en pentesting. Crear   mapas de red.                      |
|     NMAP             |     Network Mapper: herramienta de escaneo y auditoría de red.                                                        |     Escanear puertos, descubrir servicios,   versiones y sistemas operativos de dispositivos en red.    | Enumeración de puertos abiertos. Auditorías de seguridad. Detección de vulnerabilidades.                               |
|     GOBUSTER         |     Herramienta de fuerza bruta para descubrir directorios y archivos   ocultos en servidores web.                    |     Enviar múltiples solicitudes HTTP para   descubrir rutas válidas en una aplicación web.             | Fuzzing   de directorios/archivos web. Enumeración en pruebas de penetración web. Descubrimiento de recursos ocultos.    |
|     HYDRA            |     Herramienta de ataque de fuerza bruta a servicios de autenticación   remota.                                      |     Probar combinaciones de usuarios/contraseñas   sobre servicios como SSH, FTP, HTTP, etc.            | Pentesting de credenciales. Auditoría de autenticación remota. Automatización de ataques por diccionario.              |
|     SCP              |     Herramienta basada en SSH para la transferencia segura de archivos.                                               |     Copiar archivos entre sistemas remotos o   locales de forma cifrada.                                | Transferencia de evidencias. Migrar   configuraciones o binarios. Automatizar copias seguras.
|     SSH              |     Protocolo de red seguro para acceso remoto a través de una consola.                                               |     Conexión a sistemas remotos de forma segura   mediante cifrado.                                     |     - Acceso   remoto a servidores.     -   Administración de sistemas Linux.     - Túneles   SSH para acceso seguro.                          ||
|     STEGHIDE         |     Herramienta de esteganografía para ocultar o extraer información   dentro de archivos (como imágenes o audio).    |     Inserta o recupera archivos secretos en   imágenes o sonidos.                                       | Ciberseguridad forense. CTFs   (Capture The Flag). Estudio   de técnicas de ocultación.                                         |




2.	Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando.

![Cyber](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExMjAwM3Q5MTM4NXY2MXBlZm5taWx0bjRzajNsaGVmOWE5bzgyam5zMCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/HscDLzkO8EOTmgkhQP/giphy.webp)
![Cyber](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExMjAwM3Q5MTM4NXY2MXBlZm5taWx0bjRzajNsaGVmOWE5bzgyam5zMCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/VTtANKl0beDFQRLDTh/giphy.webp)
![Cyber](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExcmRuaWN4bzk3OWV5eWpiNTBiNTZkMXIzN3JzcWJ1Z2N0ZW50MG5zeSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/bGgsc5mWoryfgKBx1u/giphy.webp)
![Cyber](https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWltM210ZGIyZGxzdW0ydjBmb2FuM2lzcGVvbmpmdXU5d2ltd3JuZyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/l0IyeheChYxx2byDu/giphy.webp)





|                 Comando                 |                Función               |                         Desglose                        |              Variante 1              |         Variante 2         |     Variante 3     |
|:---------------------------------------:|:------------------------------------:|:-------------------------------------------------------:|:------------------------------------:|:--------------------------:|:------------------:|
| ip a                                    | Muestra interfaces y direcciones IP. | Utiliza el comando ip para mostrar interfaces.          | ifconfig                             | ip link                    | ip route           |
| netdiscover -i docker0 -r 172.17.0.0/24 | Descubre dispositivos en red.        | Especifica interfaz docker0 y rango IP.                 | arp-scan -l                          | netdiscover -r <IP>/24     | nmap -sn <IP>/24   |
| sudo nmap --min-rate 5000 -p- -sS -sV        | Escaneo de puertos y servicios.      | Escaneo SYN, todos los puertos, detección de servicios. | nmap -T4 -A                          | nmap -Pn -p 22,80          | nmap --script vuln |
| gobuster dir -u <url> -w <wordlist>     | Fuerza bruta de directorios web.     | Usa diccionario para buscar directorios.                | gobuster dns                         | gobuster fuzz              | dirb               |
| hydra -l user -P wordlist ssh://<IP>    | Fuerza bruta SSH.                    | Usuario fijo, diccionario, objetivo SSH.                | hydra -L users.txt -P pass.txt       | hydra -s 2222              | medusa             |
| ssh user@IP                             | Conexión remota segura.              | Conexión al host remoto con usuario.                    | ssh -p 2222                          | ssh -i key.pem             | sftp               |
| cd /ruta                                | Cambiar de directorio.               | Navega entre carpetas del sistema.                      | cd ~                                 | cd ..                      | cd -               |
| scp user@host:/ruta /destino            | Copiar archivos por SSH.             | Transferencia segura desde un host remoto.              | scp -P 2222                          | scp ./file user@host:/path | rsync -e ssh       |
| file archivo                            | Ver tipo de archivo.                 | Inspecciona metadatos del archivo.                      | file *                               | stat archivo               | exiftool archivo   |
| steghide --extract -sf archivo          | Extraer datos ocultos.               | Usa esteganografía para extraer datos.                  | steghide info archivo.jpg            | steghide embed             | zsteg archivo      |
| `echo                                   | base64 -d`                           | Decodificar base64.                                     | Convierte una cadena base64 a texto. | base64 archivo -d          | `echo texto        |
| su usuario                              | Cambiar de usuario.                  | Cambia a otra cuenta de usuario.                        | su - usuario                         | sudo su -                  | login usuario      |
| sudo -l                                 | Ver comandos permitidos.             | Muestra lo que el usuario puede hacer con sudo.         | sudo -u user comando                 | sudo -s                    | sudoedit archivo   |
| sudo ruby -e 'exec ...'                 | Escalada de privilegios.             | Ejecuta una shell como root usando Ruby.                | sudo /bin/sh                         | sudo python -c ...         | sudo perl -e ...   |
| whoami                                  | Mostrar usuario actual.              | Retorna el nombre del usuario actual.                   | id                                   | echo $USER                 | logname            |

3.	Realice un diagrama de flujo de todo el procedimiento realizado.




