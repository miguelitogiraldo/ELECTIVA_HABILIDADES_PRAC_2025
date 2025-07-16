# Taller de Electiva - Maestría en Ciberseguridad

Este taller tiene como objetivo construir un entorno controlado y seguro para prácticas de hacking ético, desarrollo seguro y pruebas de conceptos. A continuación se explica detalladamente cada uno de los pasos y herramientas involucradas:

---

## 1. ¿Para qué instalo una máquina virtual (Parallels o VMware)?

La instalación de una **máquina virtual (MV)** mediante herramientas como **Parallels (macOS)** o **VMware Workstation/Fusion** permite:

- **Aislamiento del entorno**: Se evita comprometer el sistema operativo principal durante pruebas o análisis de seguridad.
- **Simulación de entornos reales**: Podemos emular redes, sistemas operativos y configuraciones similares a un entorno corporativo.
- **Facilidad de recuperación**: A través de instantáneas (*snapshots*), se puede restaurar el sistema si algo sale mal durante un experimento o ataque controlado.
- **Multiplataforma**: Ejecutar sistemas como Kali Linux, Windows Server o Debian en un mismo equipo físico.
- **Movilidad**: Las máquinas virtuales se pueden portar fácilmente entre sistemas.

> En ciberseguridad, el uso de MVs permite realizar prácticas éticas de penetración, ingeniería inversa o análisis de malware sin riesgo para el host.

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

## 4. ¿Qué es el acceso SSH en una MV como Parallels?

**SSH (Secure Shell)** es un protocolo de red seguro que permite el acceso remoto a sistemas de forma cifrada mediante una terminal.

### ¿Por qué usar SSH en una MV?

- **Administración remota**: Permite controlar la MV Kali desde otro equipo o desde el host sin necesidad de interfaz gráfica.
- **Automatización de tareas**: Ejecutar scripts, configuraciones o pruebas desde el host hacia la MV.
- **Transferencia segura de archivos**: Usando `scp` o `rsync` con cifrado.
- **Simulación de ataques reales**: SSH permite realizar pruebas como fuerza bruta, tunneling, o prácticas de hardening del servicio.

> SSH es una de las formas más comunes de administración en servidores Linux y es fundamental para el trabajo remoto y seguro de administradores y pentesters.

---

## 5. ¿Para qué creo una cuenta de GitHub?

**GitHub** es una plataforma de control de versiones basada en `git`, ampliamente utilizada por desarrolladores, investigadores y profesionales de la ciberseguridad.

### Utilidades en este contexto:

- **Versionado de código**: Permite llevar un control detallado de tus scripts, configuraciones y cambios.
- **Documentación de prácticas**: Puedes alojar `README.md`, manuales o informes técnicos.
- **Colaboración**: Trabajar con compañeros en proyectos o laboratorios conjuntos.
- **Publicación de herramientas o exploits propios**: Puedes crear tus propios scripts y compartirlos con la comunidad.
- **Acceso a proyectos open source**: Muchas herramientas de ciberseguridad están alojadas allí (como `Metasploit`, `sqlmap`, `recon-ng`, etc.).

> GitHub no solo es una plataforma de desarrollo, también es un medio de aprendizaje, colaboración y reputación profesional en la comunidad de ciberseguridad.

---
