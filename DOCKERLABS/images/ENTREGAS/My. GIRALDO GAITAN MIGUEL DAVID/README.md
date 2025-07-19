##  TALLER INDIVIDUAL RETO DEL AMOR ❤️

1. 🛠️ Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

2. 🧠 Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando.

3. 🔁 Realice un diagrama de flujo de todo el procedimiento realizado.


## 1. 🛠️ Herramientas Empleadas

| Herramienta      | Definición                                                                 | Funcionalidad Principal                                                      | Casos de Uso Comunes                                                                 |
|------------------|----------------------------------------------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| **Docker**       | Plataforma de contenedores que permite empaquetar aplicaciones y servicios.| Crear, desplegar y gestionar entornos aislados para pruebas de ciberseguridad.| Levantar laboratorios seguros y reproducibles.                                      |
| **Nmap**         | Herramienta de escaneo de redes de código abierto.                         | Identifica dispositivos activos, servicios, puertos abiertos y sistemas operativos.| Reconocimiento de red y escaneo de vulnerabilidades.                               |
| **ARP-scan**     | Herramienta para descubrir dispositivos en una red local mediante ARP.     | Escanea rápidamente una red para descubrir hosts.                            | Enumeración de red interna en auditorías de red.                                    |
| **Hydra**        | Herramienta de fuerza bruta para cracking de contraseñas en servicios remotos.| Realiza ataques de diccionario en servicios como HTTP, SSH, FTP, etc.       | Pentesting y recuperación de credenciales.                                          |
| **File**         | Comando Unix para identificar el tipo de un archivo.                       | Determina el tipo MIME de un archivo y su estructura interna.                | Análisis forense y de ingeniería inversa.                                           |
| **Steghide**     | Herramienta de esteganografía para ocultar/extraer datos en archivos de imagen/audio.| Oculta y recupera información sensible en archivos multimedia.               | Retos CTF, protección de datos sensibles en imágenes.                               |



## 2. 🧠 Comandos Detallados y Variantes

### 🔹 Docker

```bash
docker pull raelize/docker-labs
docker run -it raelize/docker-labs
```
- **Variantes:**
  - `docker run --rm`
  - `docker run -d`
  - `docker exec -it <id> /bin/bash`

| Comando | Explicación |
|--------|-------------|
| `docker pull raelize/docker-labs` | Descarga la imagen del laboratorio 'docker-labs' desde Docker Hub para su posterior ejecución. |
| `docker run -it raelize/docker-labs` | Ejecuta la imagen descargada en modo interactivo, abriendo una terminal dentro del contenedor. |

### 🔹 ARP-scan

```bash
arp-scan --interface=eth0 --localnet
```
- **Variantes:**
  - `arp-scan 192.168.1.0/24`
  - `arp-scan --ignoredups`
  - `arp-scan -l`

| Comando | Explicación |
|--------|-------------|
| `arp-scan --interface=eth0 --localnet` | Escanea la red local en la interfaz eth0 para descubrir hosts activos usando paquetes ARP. |

### 🔹 Nmap

```bash
nmap -sV 127.0.0.1
```
- **Variantes:**
  - `nmap -A`
  - `nmap -p 80,443`
  - `nmap -O`

| Comando | Explicación |
|--------|-------------|
| `nmap -sV 127.0.0.1` | Realiza un escaneo al localhost detectando versiones de servicios disponibles en los puertos abiertos. |

### 🔹 Hydra

```bash
hydra -l admin -P rockyou.txt 127.0.0.1 http-get /login
```
- **Variantes:**
  - `hydra -L users.txt -P pass.txt ssh://192.168.0.1`
  - `hydra -t 4`
  - `hydra -V`

| Comando | Explicación |
|--------|-------------|
| `hydra -l admin -P rockyou.txt 127.0.0.1 http-get /login` | Lanza un ataque de fuerza bruta con usuario 'admin' y el diccionario 'rockyou.txt' sobre un servicio HTTP. |

### 🔹 file

```bash
file imagen.jpg
```
- **Variantes:**
  - `file *`
  - `file -i archivo`
  - `file -b archivo`

| Comando | Explicación |
|--------|-------------|
| `file imagen.jpg` | Identifica el tipo y formato de archivo de 'imagen.jpg', útil para detectar si esconde otros datos. |

### 🔹 steghide

```bash
steghide extract -sf imagen.jpg
```
- **Variantes:**
  - `steghide info imagen.jpg`
  - `steghide embed -cf cover.jpg -ef secreto.txt`
  - `steghide extract -sf imagen.jpg -p "clave"`

| Comando | Explicación |
|--------|-------------|
| `steghide extract -sf imagen.jpg` | Extrae datos ocultos en la imagen mediante esteganografía si el archivo fue previamente modificado con steghide. |

## 3. 🔁 Diagrama de Flujo del Procedimiento

```plaintext
Inicio
  │
  ▼
Despliegue de Docker
  │
  ▼
Ejecución del contenedor con laboratorio
  │
  ▼
Exploración de red con ARP-scan
  │
  ▼
Identificación de servicios con Nmap
  │
  ▼
Ataque de fuerza bruta con Hydra
  │
  ▼
Acceso al sistema y descarga de archivo sospechoso
  │
  ▼
Análisis con file
  │
  ▼
Extracción de datos con steghide
  │
  ▼
Hallazgo de bandera (flag)
  │
  ▼
Fin

