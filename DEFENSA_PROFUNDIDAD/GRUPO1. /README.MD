 # Defensa en Profundidad: Fortaleza Digital de TechSolutions Corp # 

# Presentado por: #

 * CC OSPINA JUAN
 * CC PARRA DIEGO
 * MY DOLMAN LOPEZ
 * MY LATORRE LUIS 
 * MY FUYO GIOVANNI
 * CC FABRE EDUARDO


# Contexto #
TechSolutions Corp. es una empresa global líder en el desarrollo de software y servicios en la nube, con una base de clientes masiva y una vasta cantidad de datos sensibles, incluyendo información financiera, propiedad intelectual y datos personales de clientes. Su infraestructura de TI es compleja, abarcando centros de datos locales, entornos de nube híbrida (AWS y Azure), una red de oficinas distribuidas globalmente y una fuerza laboral remota significativa.
El Incidente Es el 10 de junio de 2025. Su equipo como expertos en ciberseguridad ha detectado una serie de actividades anómalas:

# 1. Análisis de Amenazas y Vulnerabilidades #
# Amenazas identificadas: #
# Phishing dirigido con técnicas de ingeniería social # 
En el caso de los empleados que recibieron correos que suplantaban al departamento de TI, esta vulnerabilidad se presenta debido a que varios factores como, falta de educación a los usuarios del sistema asi mismo en los sistemas de correo electrónico no se contó con un sistema de Política de Seguridad de Contenido (CSP), el cual podría haber permitido identificar que los correos recibidos vienen de un dominio malicioso por lo cual no pudieron ser bloqueados a tiempo (no se mitigó seleccionando solo recibir información de dominios de confianza).

# Explotación de vulnerabilidad de día cero # 
En software no parchado (servidor en DMZ). La vulnerabilidad allí presentada se dio debido a que se tenía un servidor conectado a la estructura de la empresa el cual se encontraba no parchado, es decir, actualizado con las ultimas correcciones a su sistema de seguridad, empeorando la situación, asi mismo este servidor se encontraba en una DMZ o zona desmilitarizada es decir que no contaba con la hardenización necesaria y los sistemas de seguridad requeridos para evitar una intrusión al sistema principal. Siendo mas crítico aun debido a que se encontró una vulnerabilidad de dia cero es decir que nunca había sido identificada y que pudo ser explotada por el atacante.

# Malware introducido mediante archivo adjunto malicioso  #
Debido a la falta de educación a los usuarios acerca de los riesgos en ciberseguridad y la amenaza de archivos maliciosos, eso se presentó debido a la falta de políticas que prohíban la realización de actividades personales a través de los correos institucionales asi como ya se nombró no había un sistema de Política de Seguridad de Contenido (CSP).

# Consecuencias # 
# Movimiento lateral # 
Mediante escaneo interno y elevación de privilegios el atacante logró llegar a uno de los equipos de desarrollo de software esto a través de la generación de usuarios y claves de correo con el fin de identificar lograr privilegios de administrador.

# Persistencia a través de cuentas ocultas y tareas programadas #
El ciberatacante al parecer logró instalar malware con el fin de establecer una back door para tener comando y control sobre el equipo generando persistencia con el fin de poder llegar a su objetivo final que es la obtención de la información de las patentes tecnológicas.

# Exfiltración de datos sensibles y ransomware # 
Táctica de distracción o doble extorsión 


<img src="/Users/diegoparra/Documents/GITHUB/1.png">

# Vulnerabilidades principales: #
 # •	Gestión de parches deficiente: # Servidores web públicos con software obsoleto en la DMZ, exponiendo vulnerabilidades conocidas.
# •	Configuraciones inseguras en la nube: # Permisos excesivos en bases de datos de propiedad intelectual, facilitando la exfiltración.
# •	Falta de controles de acceso granular: # Cuentas con privilegios administrativos innecesarios, permitiendo la creación de usuarios ocultos.
# •	Concienciación insuficiente: # Empleados nuevos no capacitados en identificación de phishing o descargas maliciosas.

# 2. Principios de Defensa en Profundidad Aplicados #
La defensa en profundidad se basa en establecer múltiples capas de seguridad para crear redundancia y evitar que una sola falla comprometa toda la infraestructura. Las capas deben ser coordinadas, dinámicas y adaptables, utilizando:
* •	Segmentación de la red con claves perimetrales para cada sector de la red.
* •	Manejo de backups y espejos para resiliencia a corto plazo para cada sector de la red a través de un sistema automatizado. 
* •	Instalación de trampas de miel para desviar los ataques y poder detectarlos 
* •	Establecer un SOC el cual monitorea 24/7 la red y un CERT que responderá inmediatamente en caso de un incidente informático evitando el escalamiento de las amenazas.
* •	Contar con un IDS (sistema de detección de intrusos), y un IPS (Sistema de prevención contra intrusos), el primero detecta y el segundo detecta y bloquea ciberamenazas.
* •	Encriptación de la información en los servidores de almacenamiento on-premise y la nube esto con el fin de que si la información es sustraída no pueda se leída por el ciberatacante (encriptación en almacenamiento final).
* •	Encriptación de llave temporal en los correos, esto significa que cada mensaje que sale por los correos tiene una clave única asignada por las llaves del sistema tanto pública como privada así que si el ciberatacante logra obtener una llave por medio de un ataque de hombre en el medio solo podrá abrir un archivo, pero no podrá ver los mensajes de manera continua ya que las llaves varían constantemente.
* •	Encriptación de los canales de transmisión de datos TLS (transfer layer security) es decir se configura el protocolo https, garantizando que se previenen ataques de hombre en el medio pues los mensajes de correo viajan encriptados
* •	Configuración de políticas de mínimo privilegio para todos los usuarios es decir que no podrán tener privilegios de administrador y solo podrán acceder a los recursos mínimos necesarios para la realización de su trabajo asegurando así una compartimentación de permisos.
* •	No se permitirán las redes wifi en la empresa ni ninguna red alterna y todo deberá ser a través de cableado LAN.
* •	el servidor de dominio DNS contará con la respectiva seguridad de claves hardenizadas que deben sr cambiadas de manera constante por el departamento de TI impidiendo que se presenten debilidades por claves antiguas, asi mismo el firewall debe bloquear paginas de redes sociales etc y solo deben permitir la salida a la red de los equipos autorizados que requieran paginas (dominios) que tengan que ver con el objeto productivo de la empresa.
* •	El Servidor de Directorio Activo (Active Directory Server) debe ser protegido altamente con doble factor de autenticación para el ingreso o un sistema de token ello con el fin de lograr que un ciber atacante pueda escalar privilegios e ingresar a diferentes equipos dentro del sistema.
* •	Establecimiento en los correos de la autenticación de doble factor para asegurar la identidad de los usuarios del correo.
* •	Limitar el CORS intercambio de orígenes cruzados entre orígenes, es decir limitar a quienes no tienen o nenecitan tener contacto con dominios en internet o paginas web, asi mismo a través de este sistema configurar cuales dominios podrán ser accesados por cada usuario según su perfil de privilegios.
* •	Instalar un Servidor de Consola de Administración de Antivirus para Mantener el antivirus actualizado en todos los equipos de la red y mantener actualizado el mismo.
* •	El SOC debe presionar a TI y a la gerencia de la empresa con el fin mantener actualizadas las licencias de todos los equipos de los diferentes sotware que se usen en la empresa con el fin de evitar problemas legales y generar vulnerabilidades de dia cero.
* •	Establecer límites de tamaño de archivo: evita que los usuarios carguen archivos excesivamente grandes que podrían consumir valioso espacio de almacenamiento o ralentizar el rendimiento del sistema.
* •	Restringir tipos de archivo: Permitir la carga únicamente de los formatos necesarios. Bloquear tipos de archivo potencialmente peligrosos como .exe, .sh, .js y otros que podrían contener código malicioso.
* •	Limitar el acceso a archivos: si los usuarios no autenticados no necesitan acceso a las cargas de archivos
* •	Implementar una política de contraseñas lo suficientemente compleja evita que los usuarios establezcan contraseñas fáciles de adivinar que los atacantes puedan aprovechar.
Red sin hardenizar
 

E Red hardenizada # 
 
# 3. Capas de Defensa Propuestas #
# Capa 1: Perímetro / Red Externa #
* •	Firewall de nueva generación (NGFW) con IDS/IPS integrados.
* •	Sistema de detección de anomalías en el borde (UEBA, NTA).
* •	DNS filtering y geofencing.
* •	Segmentación de zona desmilitarizada (DMZ) con acceso limitado y monitoreado.
# Capa 2: Red Interna / Segmentación #
* •	Microsegmentación con VLANs y firewalls internos.
* •	Políticas de acceso basadas en Zero Trust Network Architecture (ZTNA).
* •	Monitoreo del tráfico lateral con herramientas NDR.


El gráfico radar que muestra el nivel de efectividad (de 0 a 5) de cada capa de defensa en profundidad en TechSolutions Corp. Como puedes ver, hay un equilibrio bastante sólido, aunque la capa de "Aplicaciones" muestra un nivel ligeramente menor, lo que podría indicar un área prioritaria para fortalecer.

$ Capa 3: Endpoint / Dispositivos #
* •	EDR con capacidades de detección y respuesta.
* •	Whitelisting de aplicaciones.
* •	Control de dispositivos USB y almacenamiento externo.
* •	Gestión de parches y actualizaciones automáticas.
# Capa 4: Aplicaciones #
* •	Revisión y escaneo estático/dinámico de seguridad en desarrollo (SAST/DAST).
* •	WAF frente a aplicaciones web expuestas.
* •	Pruebas regulares de pentesting y code review.
# Capa 5: Datos #
* •	Cifrado en reposo y en tránsito.
* •	Clasificación de datos y políticas de retención.
* •	DLP (Data Loss Prevention) para detectar exfiltración.
* •	Backups cifrados con air-gap.
# Capa 6: Identidad y Acceso #
* •	MFA en todos los accesos (usuarios y admins).
* •	IAM con RBAC (control de acceso basado en roles).
* •	Revisión periódica de privilegios.
* •	Alertas ante cambios de configuración de cuentas privilegiadas.
# Capa 7: Operaciones y Concienciación #
* •	Simulaciones de phishing y capacitación constante del personal.
* •	Red Team / Blue Team internos o externos.
* •	SOC con monitoreo 24/7.
* •	SIEM con correlación de eventos en tiempo real.

# 4. Respuesta al Incidente (Acciones Iniciales) #
# •	Contención inmediata: #
* o	Aislamiento de los endpoints comprometidos.
* o	Bloqueo de IPs maliciosas y de dominios identificados.
# •	Erradicación: #
* o	Eliminación de cuentas ocultas.
* o	Revisión de tareas programadas y scripts sospechosos.
* o	Parcheo de vulnerabilidad de día cero.
# Análisis forense: #
* o	Captura de imágenes de sistemas comprometidos.
* o	Análisis de logs y tráfico de red.
# •	Notificación: #
o	A partes interesadas internas, clientes afectados y autoridades regulatorias si aplica.

# 5. Monitoreo y Mejora Continua #
* •	Evaluaciones continuas de vulnerabilidades (VA).
* •	Auditorías de cumplimiento y simulacros de crisis.
* •	Revisión trimestral de políticas de seguridad.
* •	Actualización del marco de amenazas y riesgos (MITRE ATT&CK, CVEs).
* •	Incorporación de inteligencia de amenazas (Threat Intelligence).
* •	Automatización de parches críticos: Integración de herramientas como Microsoft Defender for Endpoint para aplicar actualizaciones en 24 horas tras su lanzamiento.
* •	Threat Intelligence integrada: Suscripción a feeds de TTPs (Tácticas, Técnicas y Procedimientos) de grupos APT para ajustar reglas de detección.
* •	Modelado de amenazas cuantitativo: Uso de frameworks como FAIR para priorizar inversiones en seguridad basadas en impacto financiero.
* •	Pruebas de resistencia cibernética: Simulaciones de crisis con escenarios combinados (ej. ransomware + filtración de datos).

# Conclusiónes #  
* La defensa en profundidad no es un destino, sino un proceso continuo de adaptación frente a un entorno de amenazas en constante evolución. Una arquitectura resiliente requiere no solo tecnología, sino cultura de seguridad, entrenamiento y una gobernanza robusta.


# Referencias Bibliográficas Actualizadas#
1.	Check Point. (2023). ¿Qué es la Defensa en Profundidad? https://www.checkpoint.com/es/cyber-hub/cyber-security/what-is-defense-in-depth/ 12
2.	Kaspersky. (2025). Vulnerabilidades y ataques de día cero. https://latam.kaspersky.com/resource-center/definitions/zero-day-exploit 13
3.	Cloudflare. (2025). ¿Qué es la defensa en profundidad? https://www.cloudflare.com/es-es/learning/security/glossary/what-is-defense-in-depth/ 2
4.	Microsoft. (2025). Respuesta a incidentes. https://www.microsoft.com/es-co/security/business/security-101/what-is-incident-response/ 8
5.	Fortinet. (2023). Defensa en profundidad. https://www.fortinet.com/lat/resources/cyberglossary/defense-in-depth 3
6.	PMG SSI. (2015). Componentes de la defensa en profundidad. https://www.pmg-ssi.com/2015/01/iso-27001-componentes-de-la-defensa-en-profundidad/ 4
7.	Check Point. (2024). Fases de respuesta a incidentes. https://www.checkpoint.com/es/cyber-hub/cyber-security/what-is-incident-response/the-6-phases-of-an-incident-response-plan/ 7
8.	EasyDMARC. (2025). Cómo detener el ransomware. https://easydmarc.com/blog/es/como-detener-el-ransomware-en-tiempo-real/ 5
9.	TBSEK. (2025). Mejora continua en ciberseguridad. https://tbsek.mx/articulos/2025/04/45.mejoracontinua.html 9
10.	Nacata. (2023). Plan de mejora continua. https://nacata.io/mejora-continua/ 10


