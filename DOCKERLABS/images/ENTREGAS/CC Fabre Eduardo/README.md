## **Taller Individual**

1.Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

2.Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando.

3.Realice un diagrama de flujo de todo el procedimiento realizado.

**Desarrollo**

## 1. Herramientas Utilizadas

| Herramienta   | Definición                                                                 | Funcionalidad                                                         | Casos de uso                                                        |
|---------------|----------------------------------------------------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------|
| netdiscover   | Escáner ARP pasivo para detectar hosts en la red LAN                      | Detectar IPs activas mediante respuestas ARP                          | Reconocimiento de red, pentesting inicial                          |
| arp-scan      | Escáner activo que envía paquetes ARP para mapear dispositivos LAN        | Mapear red local con IPs y MACs visibles                              | Auditoría de red, descubrimiento de hosts                          |
| tcpdump       | Captura y analiza paquetes de red                                         | Inspección de tráfico, filtrado por protocolo                         | Análisis de tráfico, detección de ataques                          |
| hydra         | Ataque de fuerza bruta para recuperación de credenciales                  | Descubrir contraseñas en varios servicios (HTTP, SSH, FTP, etc.)      | Pentesting, evaluación de contraseñas                             |
| steghide      | Herramienta de esteganografía para ocultar/extraer archivos en imágenes   | Extraer datos ocultos dentro de imágenes o audios                     | Análisis forense, CTFs                                             |
| binwalk       | Analiza y extrae contenido oculto en archivos binarios                    | Extraer automáticamente segmentos embebidos en archivos               | Forense digital, ingeniería inversa                               |
| file          | Identifica tipo de archivo o contenido binario                            | Detecta el formato real de archivos                                   | Verificación previa a análisis binario                            |

## 2. Comandos Detallados y Variantes

### 1. `ip a`
- **Función:** Muestra la configuración de red y direcciones IP.
- **Variantes:**
  - `ip a show eth0` – Muestra IP de una interfaz específica.
  - `ip link show` – Estado de las interfaces.
  - `ip route` – Tabla de enrutamiento.

---

### 2. `netdiscover`
- **Función:** Escanea hosts ARP activos en red local.
- **Variantes:**
  - `netdiscover -r 192.168.1.0/24`
  - `netdiscover -i eth0`
  - `netdiscover -p`

---

### 3. `arp-scan`
- **Función:** Escaneo ARP activo para descubrir dispositivos.
- **Variantes:**
  - `arp-scan -l`
  - `arp-scan --localnet`
  - `arp-scan --retry=3`

---

### 4. `tcpdump`
- **Función:** Captura paquetes de red.
- **Variantes:**
  - `tcpdump -i any`
  - `tcpdump -n -X port 80`
  - `tcpdump -w captura.pcap`

---

### 5. `hydra`
- **Función:** Fuerza bruta para credenciales.
- **Ejemplo:** `hydra -l admin -P rockyou.txt 172.17.0.2 http-get /login`
- **Variantes:**
  - `hydra -L users.txt -P passwords.txt ssh://192.168.1.5`
  - `hydra -l admin -P dict.txt ftp://192.168.1.5`
  - `hydra -V -l user -P pass.txt rdp://192.168.1.10`

---

### 6. `steghide`
- **Función:** Extraer datos ocultos en imágenes/audio.
- **Variantes:**
  - `steghide info imagen.jpg`
  - `steghide embed -cf imagen.jpg -ef secreto.txt`
  - `steghide extract -sf imagen.jpg -xf salida.txt`

---

### 7. `binwalk`
- **Función:** Escaneo y extracción de contenido embebido.
- **Variantes:**
  - `binwalk imagen.jpg`
  - `binwalk -e -M imagen.jpg`
  - `binwalk -D 'png:png_extract' imagen.jpg`

---

### 8. `file`
- **Función:** Determina el tipo de archivo.
- **Variantes:**
  - `file -i archivo.jpg`
  - `file *`
  - `file -b archivo`
 
    
