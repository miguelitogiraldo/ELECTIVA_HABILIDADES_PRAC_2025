
### 1. ¿Qué es el *Spoofing*?

El **spoofing** (suplantación) es una técnica utilizada por atacantes para **fingir una identidad falsa** con el fin de engañar a un sistema, red o usuario. Es una táctica común en ataques de ingeniería social, interceptación de datos o evasión de controles de seguridad.

---

### 2. Tipos de Spoofing

| Tipo de Spoofing   | Descripción                                      | Objetivo común                      |
| ------------------ | ------------------------------------------------ | ----------------------------------- |
| **IP Spoofing**    | Falsifica la dirección IP del remitente          | Evasión de firewalls, DDoS, MITM    |
| **ARP Spoofing**   | Envenena la caché ARP de una red local           | Interceptar tráfico (MITM)          |
| **DNS Spoofing**   | Responde con direcciones falsas a peticiones DNS | Redirigir a sitios falsos           |
| **Email Spoofing** | Falsifica el remitente de un correo electrónico  | Phishing, fraude                    |
| **Web Spoofing**   | Clona una web legítima                           | Robar credenciales                  |
| **MAC Spoofing**   | Cambia la dirección MAC de un dispositivo        | Evadir filtros, suplantar identidad |

---

### 3. Herramientas comunes utilizadas en ataques de spoofing

| Herramienta               | Tipo de ataque     | Observaciones                   |
| ------------------------- | ------------------ | ------------------------------- |
| `arpspoof` / `dsniff`     | ARP Spoofing       | Redireccionamiento de tráfico   |
| `ettercap`                | ARP y DNS Spoofing | GUI y CLI para sniffing         |
| `responder`               | SMB/DNS Spoofing   | Robo de hashes en redes Windows |
| `msfconsole` (Metasploit) | Diversos           | Exploits automatizados          |

---

### 4. Riesgos de Seguridad

* **Intercepción de credenciales** (usuario/contraseña)
* **Redirección a sitios maliciosos**
* **Instalación de malware**
* **Evasión de controles de acceso**
* **Compromiso de comunicaciones internas**

---

### 5. Prevención y Mitigación

#### A nivel de red:

* Implementar **seguridad en switches** (como Dynamic ARP Inspection).
* Usar **VPNs** para cifrar el tráfico.
* Segmentar la red y aplicar **firewalls internos**.

#### A nivel de sistema:

* Utilizar **software antivirus y antiphishing actualizado**.
* Configurar correctamente los **servidores DNS**.
* Activar **SPF, DKIM y DMARC** para autenticación de correos.

#### A nivel de monitoreo:

* Usar **IDS/IPS** para detectar patrones anómalos.
* Auditar los logs de red y DNS.
* Escanear vulnerabilidades regularmente (Nessus, OpenVAS).

---

### 6. Buenas prácticas

* Capacitar a los usuarios en **reconocimiento de phishing y suplantación**.
* No confiar ciegamente en direcciones IP o remitentes.
* Validar certificados SSL y URLs al acceder a sitios sensibles.

---


**Herramientas**

- Wireshark. (https://www.wireshark.org/)

- TCPDump. (https://www.tcpdump.org/)

- WinDump  (https://www.winpcap.org/windump/)


---
# **TALLER.**

Realizar la práctica Guia_MITM_ARP_POISSON_JON.pdf que se encuentra en esta carpeta. 
Se presenta vídeo-Guía para efectos de apoyo.




[![Ver el video en YouTube](https://img.youtube.com/vi/GDd80_9meYs/0.jpg)](http://www.youtube.com/watch?v=GDd80_9meYs)




# Referencias.

- https://www.cloudns.net/blog/tcpdump-for-beginners-what-it-is-how-to-install-and-key-commands/
- https://youtu.be/7ZJAeJaxvAc?si=XITrcdcelbshBHZw
