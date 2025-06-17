# Defensa en Profundidad: Fortaleza Digital de TechSolutions Corp #

# Presentado por: #
  CC OSPINA JUAN
  CC PARRA DIEGO
  MY DOLMAN LOPEZ
  MY LATORRE LUIS
  MY FUYO GIOVANNI
  CC FABRE EDUARDO


# Contexto #
TechSolutions Corp. es una empresa global líder en el desarrollo de software y servicios en la nube, con una base de clientes masiva y una vasta cantidad de datos sensibles, incluyendo información financiera, propiedad intelectual y datos personales de clientes. Su infraestructura de TI es compleja, abarcando centros de datos locales, entornos de nube híbrida (AWS y Azure), una red de oficinas distribuidas globalmente y una fuerza laboral remota significativa.
El Incidente Es el 10 de junio de 2025. Su equipo como expertos en ciberseguridad ha detectado una serie de actividades anómalas:

# 1. Análisis de Amenazas y Vulnerabilidades #
Amenazas identificadas:
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

