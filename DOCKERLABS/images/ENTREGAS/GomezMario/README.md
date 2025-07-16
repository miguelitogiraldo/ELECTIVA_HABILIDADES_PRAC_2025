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

- **Entornos replicables y portables**: Puedes crear contenedores con servicios vulnerables para prácticas controladas.
- **Aislamiento de herramientas**: Ejecutar múltiples versiones de una misma herramienta sin conflicto con el sistema base.
- **Automatización de laboratorios**: Crear laboratorios de ciberseguridad con scripts reproducibles (por ejemplo, mediante `docker-compose`).
- **Reducción de espacio y recursos**: Los contenedores son más livianos que las VMs tradicionales.

> En el contexto de ciberseguridad, Docker permite crear entornos de prueba rápidos para explotación de vulnerabilidades, CI/CD seguros, honeypots y entornos simulados.

---


