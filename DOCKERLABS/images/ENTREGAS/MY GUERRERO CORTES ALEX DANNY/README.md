**Taller Individual**

1. Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

| Herramienta | Definición | Funcionalidad | Casos de uso |
|-------------|------------|----------------|--------------|
| **Docker** | Plataforma de virtualización ligera basada en contenedores. | Permite ejecutar laboratorios aislados y reproducibles. | Laboratorios de ciberseguridad, despliegue de microservicios, testing. |
| **nmap** | Herramienta de escaneo de redes. | Descubre hosts y servicios en una red. | Reconocimiento en pentesting, auditorías de red. |
| **tcpdump** | Sniffer de línea de comandos. | Captura tráfico de red en tiempo real. | Análisis forense, troubleshooting de red. |
| **Hydra** | Herramienta de fuerza bruta para servicios de red. | Automatiza ataques de diccionario sobre servicios. | Pentesting de contraseñas débiles, auditorías de seguridad. |
| **steghide** | Herramienta de esteganografía. | Oculta y extrae datos en imágenes/audio. | Ocultación de mensajes, análisis forense. |
| **file** | Comando Unix para identificar tipos de archivos. | Muestra el tipo MIME o contenido del archivo. | Reconocimiento forense, scripting para procesar archivos. |

2. Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando.

![Descripción](Imagenes/Imagen%201.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `docker run -it kalilinux/kali-rolling` | `docker`: cliente de Docker <br>`run`: crea y ejecuta un contenedor <br>`-it`: modo interactivo con terminal <br>`kalilinux/kali-rolling`: imagen a usar | Despliega un contenedor interactivo de Kali Linux para trabajar en el laboratorio. | - `docker ps` (lista contenedores activos) <br> - `docker stop <ID>` (detiene contenedor) <br> - `docker exec -it <ID> /bin/bash` (accede al contenedor en ejecución) |

![Descripción](Imagenes/Imagen%202.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `nmap -sV -Pn -p- 172.19.0.3` | `-sV`: detección de versión de servicios <br>`-Pn`: omite ping discovery <br>`-p-`: todos los puertos (1-65535) <br>`IP`: objetivo | Realiza escaneo completo de puertos y detecta versiones de servicios, incluso si el host filtra ping. | - `nmap -A <IP>` (escaneo agresivo) <br> - `nmap -sS <IP>` (SYN scan) <br> - `nmap -T4 <IP>` (ajusta velocidad) |

![Descripción](Imagenes/Imagen%203.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `tcpdump -i eth0 -w captura.pcap` | `-i eth0`: interfaz de red <br>`-w captura.pcap`: escribe captura en archivo | Captura el tráfico de red en la interfaz especificada y lo guarda en un archivo para análisis posterior. | - `tcpdump -nn` (no resuelve nombres) <br> - `tcpdump port 80` (filtra por puerto) <br> - `tcpdump -r captura.pcap` (lee archivo) |

![Descripción](Imagenes/Imagen%204.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `hydra -l admin -P rockyou.txt ftp://172.19.0.3` | `-l admin`: usuario objetivo <br>`-P rockyou.txt`: diccionario de contraseñas <br>`ftp://IP`: servicio y objetivo | Realiza ataque de fuerza bruta para encontrar la contraseña del usuario especificado en el servicio FTP. | - `-L usuarios.txt` (lista de usuarios) <br> - `-s <puerto>` (define puerto) <br> - `-t 16` (define número de tareas en paralelo) |

![Descripción](Imagenes/Imagen%205.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `file imagen.jpg` | `file`: comando de identificación de tipos de archivo <br>`imagen.jpg`: archivo objetivo | Detecta el tipo de contenido de un archivo (MIME, tipo, formato). | - `file *` (todos los archivos del directorio) <br> - `file -i imagen.jpg` (solo MIME) <br> - `file -z archivo` (archivos comprimidos) |

![Descripción](Imagenes/Imagen%206.jpg)

| Comando | Desglose | Explicación | Variantes (si aplica) |
|---------|----------|-------------|-----------------------|
| `steghide extract -sf imagen.jpg` | `extract`: orden de extracción <br>`-sf imagen.jpg`: archivo de entrada | Extrae el contenido oculto en un archivo mediante esteganografía. | - `steghide embed -cf imagen.jpg -ef secreto.txt` (oculta un archivo) <br> - `steghide info imagen.jpg` (muestra info del contenedor) <br> - `steghide --help` (ayuda) |

3. Realice un diagrama de flujo de todo el procedimiento realizado.

![Descripción](Imagenes/Imagen%207.jpg)
