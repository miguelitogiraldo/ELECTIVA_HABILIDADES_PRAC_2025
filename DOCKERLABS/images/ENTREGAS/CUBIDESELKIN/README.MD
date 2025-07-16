#  DockerLabs - Reto CTF “Amor”

##  Objetivo del Laboratorio

El objetivo de este reto fue aplicar técnicas de ciberseguridad ofensiva mediante el despliegue de un entorno CTF utilizando **Docker**. Se resolvieron desafíos progresivos utilizando herramientas como **Nmap**, **Hydra**, **Gobuster**, **Steghide**, entre otras, orientadas a la explotación y escalada de privilegios.

---

## 🛠 Herramientas y Funcionalidades

| Herramienta   | Descripción breve             | Funcionalidad principal               | Casos de uso típicos                  |
|---------------|-------------------------------|---------------------------------------|---------------------------------------|
| **Docker**    | Plataforma de contenedores     | Ejecutar entornos aislados            | Simular laboratorios CTF              |
| **Nmap**      | Escáner de red                 | Detectar puertos y servicios activos  | Enumeración de red inicial            |
| **Netdiscover** | Descubrimiento ARP           | Identificar IPs en red local          | Encontrar contenedores en Docker      |
| **Gobuster**  | Fuzzing HTTP                   | Enumerar rutas ocultas en servidores  | Detectar páginas sensibles            |
| **Hydra**     | Fuerza bruta de credenciales   | Automatizar ataques de login          | Descifrar contraseñas débiles         |
| **Steghide**  | Esteganografía                 | Extraer datos ocultos en imágenes     | Forense digital                       |
| **SCP**       | Copia remota segura            | Transferencia de archivos vía SSH     | Extraer evidencia                     |
| **Base64**    | Codificación binaria a texto   | Decodificar cadenas ocultas           | Análisis de contraseñas               |

---

##  Ejercicio Práctico Paso a Paso

###  Transferencia del reto a Kali

```bash
scp -r amor kali@192.168.1.12:/home/kali/Documents/













