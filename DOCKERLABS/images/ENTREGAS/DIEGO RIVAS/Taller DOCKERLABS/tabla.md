Taller DOCKERLABS

1.	Realizar una investigación individual de cada una de las herramientas empleadas. Sintetice el resultado mediante un cuadro que explique su definición, funcionalidad y casos de uso.

| Herramienta                | Definición                                                                                          | Funcionalidad                                                                                           | Casos de Uso                                                                                       |
|----------------------------|-----------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Docker                     | Plataforma de contenedores que permite crear, implementar y ejecutar aplicaciones mediante contenedores ligeros. | Aislamiento de procesos, despliegue de servicios, empaquetado de aplicaciones, escalabilidad, CI/CD.    | Entornos DevOps, despliegue en la nube, pruebas automatizadas, microservicios.                     |
| Docker Security Playground (DSP) | Entorno basado en Docker para crear laboratorios prácticos de seguridad de red usando microservicios y docker-compose. | Simulación de ataques (scanning, exploit, post-exploit), creación de entornos vulnerables, educación práctica. | Capacitación en ciberseguridad, pruebas de vulnerabilidades, aprendizaje de metodologías ofensivas. |
| Labtainers                 | Framework para la creación de laboratorios de ciberseguridad parametrizados usando contenedores Docker. | Automatización del despliegue y evaluación de ejercicios, personalización por estudiante, recolección de resultados. | Educación en seguridad informática, ejercicios en universidades y academias militares.             |
| Docker-sec                 | Módulo de seguridad Linux basado en AppArmor que protege contenedores Docker a lo largo de su ciclo de vida. | Generación automática de perfiles AppArmor, protección contra vulnerabilidades de red y escalamiento de privilegios. | Protección de contenedores en producción, ambientes seguros multiusuario.                          |
| LiCShield                  | Generador de perfiles AppArmor que


2.	Explicar en detalle cada uno de los comandos empleados realizando un desglose del mismo y citando al menos tres alternativas (si aplica) de variantes del comando.


| COMANDO PRINCIPAL | DESGLOSE SINTÁCTICO | DESCRIPCIÓN FUNCIONAL | ALTERNATIVAS / VARIANTES |
|-------------------|---------------------|-----------------------|--------------------------|
| docker run -d --name kali --network lab_net kalilinux/kali-rolling | docker run: ejecuta un contenedor <br> -d: modo 'detached' <br> --name kali: asigna nombre <br> --network lab_net: conecta a red <br> kalilinux/kali-rolling: imagen base | Lanza un contenedor Kali Linux conectado a una red definida para realizar pruebas de penetración y análisis de red. | -it: modo interactivo <br> --rm: elimina al salir <br> -v $(pwd):/data: monta volumen |
| docker network create lab_net | docker network create: crea una red <br> lab_net: nombre de la red | Permite a varios contenedores comunicarse de forma aislada, útil para simular entornos de red segura o vulnerable. | --driver bridge <br> --subnet=192.168.1.0/24 <br> --internal |
| trivy image nombre_imagen | trivy: análisis de vulnerabilidades <br> image: escanea imagen Docker <br> nombre_imagen: objetivo | Realiza un escaneo estático para identificar CVEs, configuraciones débiles o paquetes vulnerables. | trivy fs /ruta <br> trivy config /ruta <br> trivy repo https://... |
| falco -c falco_rules.yaml | falco: motor de detección <br> -c: carga reglas personalizadas | Detecta comportamientos sospechosos en tiempo de ejecución en contenedores. | falco -r reglas_adicionales.yaml <br> falco -o log_stderr=true <br> falco -d |
| lic-sec generate --image nombre_imagen | lic-sec generate: genera perfil AppArmor <br> --image: imagen objetivo | Crea perfiles de control de acceso limitando privilegios del contenedor según comportamiento. | --output perfil.apparmor <br> --runtime=60 <br> --train /ruta |
| docker-compose up -d | docker-compose: orquestación <br> docker-compose up: inicia servicios <br> -d: segundo plano | Levanta un conjunto de servicios de red definidos en YAML como si fuera un laboratorio completo. | docker-compose up --build <br> docker-compose down <br> docker-compose logs |


3.	Realice un diagrama de flujo de todo el procedimiento realizado.

<img width="900" height="1210" alt="image" src="https://github.com/user-attachments/assets/b39cab5e-6b7d-4668-9ce5-0aa07cafe24e" />
