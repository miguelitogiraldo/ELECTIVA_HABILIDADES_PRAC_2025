1. Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

| **Herramienta** | **Definición** | **Funcionalidad** | **Casos de Uso** |
|------------------|----------------|--------------------|------------------|
| **Docker**       | Plataforma de contenedores para desplegar aplicaciones de forma aislada. | Ejecutar entornos de laboratorio sin alterar el sistema base. | Simulación de entornos vulnerables, pruebas de seguridad. |
| **Nmap**         | Escáner de redes y puertos. | Identifica servicios activos, sistemas operativos y configuraciones. | Pentesting, auditorías de red, inventario de sistemas. |
| **Netdiscover**  | Herramienta ARP para detectar hosts activos. | Descubre dispositivos conectados en la misma red local. | Reconocimiento en redes desconocidas. |
| **Hydra**        | Herramienta para fuerza bruta de credenciales. | Intenta contraseñas sobre servicios como SSH, FTP, HTTP. | Test de resistencia de contraseñas, recuperación de acceso. |
| **SCP**          | Comando para copiar archivos entre sistemas por SSH. | Transfiere archivos de forma segura. | Backup remoto, paso de archivos entre VMs. |
| **Steghide**     | Herramienta de esteganografía. | Oculta y extrae datos en archivos multimedia. | CTFs, protección de información, ocultamiento de datos. |
| **File**         | Identifica el tipo de archivo. | Muestra tipo MIME y codificación. | Análisis forense, clasificación de archivos. |


2. Explicar en detalle cada uno de los comandos empleados en el anterior CTF; realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando para las herramientas empleadas, este punto amplia el ejercicio anterior.

2.1. COMANDO: DOCKER PULL RAIOLAB/amor

DESCRIPCION: Descarga la imagen del repositorio

VARIANTES: 
DOKER RUN: Ejecuta el contenero directamente

DOKER IMAGEN: Lista de imagenes descargadas

DOKER RMI: Elimina una imagen

2.2. COMANDO: NETDISCOVER -i eth0 -r 172.17.0.0/16

Descripción: Escaneo ARP para encontrar dispositivos en la red 172.17.0.0/16 usando la interfaz eth0.

•	Variantes:

i wlan0: Usa interfaz WiFi.

o	-r 192.168.1.0/24: Rango de red diferente.

o	-P: Muestra en modo pasivo.




3.    
