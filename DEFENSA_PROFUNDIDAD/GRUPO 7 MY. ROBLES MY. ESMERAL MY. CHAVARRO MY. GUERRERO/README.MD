Escuela Superior de Guerra 'General Rafael Reyes Prieto'

"Defensa en Profundidad: Fortaleza Digital de \"TechSolutions Corp.\"

My. Chavarro Gutiérrez Luis Alberto

My. Esmeral Madrid Diego Alejandro

My. Guerrero Cortes Alex Danny

My. Robles Ocampo Edna Giannine

Mando y Liderazgo

TC. Juan Manuel Navia López

Curso de Estado Mayor 2025

15 de Junio de 2025

# Defensa en Profundidad: Fortaleza Digital de \"TechSolutions Corp.\" {#defensa-en-profundidad-fortaleza-digital-de-techsolutions-corp. .unnumbered}

**Resumen del Incidente**

El 10 de junio de 2025, TechSolutions Corp., una empresa global líder en
software y servicios en la nube, fue víctima de un ciberataque avanzado
en tres fases. El ataque comenzó con correos de phishing sofisticados,
explotación de una vulnerabilidad de día cero en un servidor en la DMZ,
y la ejecución de malware desde redes sociales. Posteriormente, los
atacantes lograron moverse lateralmente por la red, escalar privilegios
y establecer persistencia en el entorno, con el objetivo final de
exfiltrar datos confidenciales y desplegar ransomware.

# Análisis de Amenazas y Vulnerabilidades

## Fase 1 - Vectores de Ataque Iniciales {#fase-1---vectores-de-ataque-iniciales .unnumbered}

-   Phishing dirigido a empleados simulando comunicaciones del
    departamento de TI.

-   Explotación de vulnerabilidad de día cero en servidor web obsoleto
    ubicado en la DMZ.

-   Malware descargado desde redes sociales a través de archivos
    adjuntos falsos.

## Fase 2 - Movimiento Lateral y Persistencia {#fase-2---movimiento-lateral-y-persistencia .unnumbered}

-   Compromiso de una estación de trabajo mediante credenciales robadas.

-   Escaneo interno de red y escalamiento de privilegios.

-   Creación de cuentas ocultas y tareas programadas maliciosas.

## Fase 3 - Exfiltración / Destrucción {#fase-3---exfiltración-destrucción .unnumbered}

-   Robo de datos críticos (propiedad intelectual y código fuente).

-   Tráfico saliente inusual hacia IPs no reconocidas.

-   Infección por ransomware en servidores clave.

# Principios de Defensa en Profundidad

Cada capa debe ser independiente y complementaria, abarcando desde el
perímetro de la red hasta la concienciación del usuario.

Principios clave:

-   Redundancia de controles.

-   Diversidad de tecnologías y enfoques.

-   Minimización de la superficie de ataque.

-   Detección y respuesta rápida.

-   Educación y concienciación continua.

```{=html}
<!-- -->
```
-   Capas múltiples de seguridad: Aplicar barreras en todas las etapas
    del modelo OSI (de la capa 1 a la 7).

-   Redundancia: Varios controles para un mismo riesgo.

-   Segmentación de acceso: Limitar el movimiento lateral.

-   Principio de menor privilegio: Acceso solo a lo estrictamente
    necesario.

-   Supervisión constante: Monitoreo y detección temprana de amenazas.

#### **Capa 1: Perímetro / Red Externa** {#capa-1-perímetro-red-externa .unnumbered}

-   Principio aplicado: Capas múltiples y supervisión constante.

-   Aplicación: Se implementan firewalls de próxima generación (NGFW),
    IDS/IPS y filtrado DNS para impedir accesos no autorizados y
    detectar tráfico sospechoso desde la Internet. Se aplican listas
    negras, geobloqueo y protección contra ataques DDoS.

-   Relación con OSI: Corresponde principalmente a las capas 3 y 4 (Red
    y Transporte), al controlar el flujo de paquetes.

-   Mitigación: Implementar *firewalls de próxima generación (NGFW)* y
    *filtrado DNS seguro* para bloquear tráfico malicioso y prevenir
    ataques desde dominios comprometidos.

-   Justificación: Esto impide accesos no autorizados y evita que
    ataques como la explotación de la vulnerabilidad de día cero lleguen
    a la red interna.

#### **Capa 2: Red Interna / Segmentación** {#capa-2-red-interna-segmentación .unnumbered}

-   Principio aplicado: Segmentación de acceso y redundancia.

-   Aplicación: Las redes se dividen en zonas lógicas (por función,
    criticidad o confidencialidad) mediante VLANs y firewalls internos.
    Esto evita que un atacante pueda moverse libremente dentro de la
    organización si compromete un sistema.

-   Relación con OSI: Aplica a la capa 2 (Enlace de Datos) y capa 3
    (Red).

-   Mitigación: Aplicar *segmentación de red con VLANs y
    microsegmentación*, junto con *firewalls internos*.

-   Justificación: Limita el movimiento lateral del atacante una vez
    dentro, conteniendo el compromiso a una zona específica.

#### **Capa 3: Endpoint / Dispositivos** {#capa-3-endpoint-dispositivos .unnumbered}

-   Principio aplicado: Supervisión constante y menor privilegio.

-   Aplicación: En los dispositivos se instalan EDR, control de puertos
    USB, políticas de actualización automatizadas y antivirus con IA. Se
    restringen privilegios de administrador.

-   Relación con OSI: Incluye desde la capa 1 (Física) hasta la 5
    (Sesión), según el tipo de dispositivo

-   Mitigación: Instalar soluciones *EDR (Endpoint Detection and
    Response)* y deshabilitar el uso no autorizado de periféricos (como
    USB).

-   Justificación: Detecta rápidamente actividad sospechosa en los
    dispositivos y evita la persistencia o ejecución de malware como el
    recibido por el empleado desde LinkedIn.

#### **Capa 4: Aplicaciones** {#capa-4-aplicaciones .unnumbered}

-   Principio aplicado: Capas múltiples y segmentación lógica.

-   Aplicación: Uso de WAF, análisis estático/dinámico de código,
    revisiones manuales y DevSecOps. Las aplicaciones tienen
    autenticación reforzada y validación de entradas para evitar
    inyecciones.

-   Relación con OSI: Capa 7 (Aplicación), directamente relacionada con
    la interacción del usuario.

-   Mitigación: Desplegar un *Web Application Firewall (WAF)* y
    actualizar el software obsoleto de gestión de proyectos en la DMZ.

-   Justificación: Previene la explotación de vulnerabilidades conocidas
    y protege contra ataques dirigidos a servicios web.

#### **Capa 5: Datos** {#capa-5-datos .unnumbered}

-   Principio aplicado: Redundancia y menor privilegio.

-   Aplicación: Clasificación de información, políticas de retención,
    cifrado AES-256, sistemas DLP y respaldo automatizado. El acceso a
    datos está restringido según el rol.

-   Relación con OSI: Capas 6 y 7 (Presentación y Aplicación), enfocadas
    en formato, cifrado y uso de los datos.

-   Mitigación: Cifrar bases de datos sensibles en reposo y tránsito, y
    aplicar soluciones *DLP (Prevención de Pérdida de Datos)*.

-   Justificación: Aunque un atacante acceda a los datos, estos no serán
    legibles; además, se evita su exfiltración no autorizada.

#### **Capa 6: Identidad y Acceso** {#capa-6-identidad-y-acceso .unnumbered}

-   Principio aplicado: Menor privilegio y redundancia.

-   Aplicación: Gestión de identidades con RBAC (Control de Acceso
    Basado en Roles), autenticación multifactor (MFA), expiración
    automática de sesiones, monitoreo de accesos y revisión periódica de
    permisos.

-   Relación con OSI: Capas 5 a 7 (Sesión, Presentación y Aplicación),
    por su vinculación con la validación y gestión de sesiones.

-   Mitigación: Activar *autenticación multifactor (MFA)* y aplicar
    *principios de mínimo privilegio* con auditorías periódicas de
    cuentas.

-   Justificación: Evita que el robo de credenciales permita el acceso a
    recursos críticos y ayuda a identificar cuentas sospechosas, como
    las creadas por el atacante.

#### **Capa 7: Operaciones y Concienciación** {#capa-7-operaciones-y-concienciación .unnumbered}

-   Principio aplicado: Supervisión constante y defensa proactiva.

-   Aplicación: Capacitación continua al personal, campañas de
    concienciación, simulacros de phishing, políticas claras y
    procedimientos documentados. Se mide la cultura de seguridad
    organizacional.

-   Relación con OSI: Transversal, ya que involucra a los usuarios que
    interactúan con todos los niveles del sistema.

-   Mitigación: Ejecutar campañas regulares de *simulacros de phishing*
    y entrenamientos obligatorios en ciberseguridad.

-   Justificación: Reduce la probabilidad de éxito de ataques basados en
    ingeniería social, como el phishing recibido por los empleados.

# Respuesta al Incidente

Pasos iniciales:

-   Contención: Aislar los sistemas comprometidos (estaciones de
    trabajo, servidores afectados) para evitar la propagación.

-   Erradicación: Eliminar malware, cuentas ocultas y tareas programadas
    maliciosas.

-   Análisis: Revisar logs, identificar el alcance del ataque y los
    datos afectados.

-   Restauración: Recuperar sistemas desde backups limpios y verificar
    la integridad.

-   Comunicación: Notificar a las partes interesadas y cumplir con las
    obligaciones legales y regulatorias.

-   Revisión: Analizar el incidente para identificar mejoras en los
    controles y procesos.

# Monitoreo y Mejora Continua

-   Implementar un SIEM (Security Information and Event Management) para
    monitoreo centralizado y correlación de eventos.

-   Realizar pruebas de penetración y auditorías de seguridad
    periódicas.

-   Actualizar y probar regularmente los planes de respuesta a
    incidentes.

-   Revisar y ajustar las políticas de seguridad según nuevas amenazas y
    lecciones aprendidas.

-   Fomentar la cultura de reporte de incidentes y aprendizaje continuo
    en toda la organización.

# Monitoreo y mejora continua

La estrategia de defensa en profundidad de TechSolutions Corp. debe
complementarse con un modelo de monitoreo y mejora continua que permita
anticiparse a nuevas amenazas y adaptarse de manera proactiva. Para
ello, se recomienda implementar un sistema SIEM (Security Information
and Event Management), el cual centraliza la recolección de logs y
permite correlacionar eventos en tiempo real, facilitando la detección
de incidentes y comportamientos anómalos.

Asimismo, es fundamental revisar y actualizar constantemente las
políticas de seguridad con base en lecciones aprendidas y cambios en el
panorama de amenazas. La realización periódica de pruebas de penetración
y auditorías de seguridad permite identificar vulnerabilidades antes de
que puedan ser explotadas.

Adicionalmente, los planes de respuesta a incidentes deben ser validados
y mejorados regularmente mediante simulacros prácticos. Por último,
fomentar una cultura organizacional orientada al reporte oportuno de
incidentes y al aprendizaje continuo consolida la resiliencia digital,
involucrando a todos los niveles del personal en la protección activa de
los activos informáticos.

# Conclusiones {#conclusiones .unnumbered}

-   La defensa en profundidad es indispensable en entornos complejos y
    distribuidos, como los que maneja TechSolutions Corp., ya que
    permite mitigar eficazmente ataques avanzados y persistentes
    mediante capas complementarias de seguridad.

-   El ataque descrito evidencia cómo múltiples vectores pueden
    comprometer la infraestructura digital si no existen controles
    robustos y redundantes. Desde el phishing inicial hasta el
    despliegue de ransomware, cada fase pudo haberse contenido con una
    adecuada implementación de controles por capa.

-   La aplicación de los principios de defensa en profundidad,
    vinculados al modelo OSI, proporciona una arquitectura resiliente,
    asegurando que si una barrera falla, otras puedan contener el
    incidente y limitar su propagación.

-   El principio de menor privilegio, la segmentación de redes, la
    autenticación multifactor y el monitoreo continuo son pilares claves
    para reducir el impacto y la superficie de ataque. En particular,
    los controles sobre identidades, endpoints y datos deben mantenerse
    actualizados y adaptados al contexto.

-   La concienciación del personal y la respuesta organizada al
    incidente son tan importantes como las herramientas técnicas. La
    cultura de ciberseguridad debe formar parte integral de la operación
    empresarial.

-   Finalmente, la mejora continua a través de monitoreo, auditorías,
    simulaciones de ataques y revisión de políticas es esencial para
    mantener la estrategia efectiva frente a nuevas amenazas, dado el
    entorno dinámico del ciberespacio.

**\
**

# Bibliografía {#bibliografía .unnumbered}

Instituto Nacional de Estándares y Tecnología. (2018). Computer Security
Incident Handling Guide (NIST SP 800-61 Rev. 2).
https://doi.org/10.6028/NIST.SP.800-61r2

ISO/IEC 27005:2022 -- Information security, cybersecurity and privacy
protection -- Guidance on managing information security risks.

