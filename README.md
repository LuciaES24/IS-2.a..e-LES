# IS-2.a..e-LES

# Resumen Unidad 2: Detección y análisis de incidentes de seguridad

## 2.1.-Taxonomía de incidentes
Un incidente de ciberseguridad es un evento no planificado que puede comprometer la seguridad de la información y puede afectar a la integridad, confidencialidad y disponibilidad de los datos.
Fases de un incidente:
1. Preparación.
2. Identificación.
3. Contención.
4. Erradicación.
5. Recuperación.
6. Lecciones aprendidas.

La gestión de estos incidentes es algo indispensable en la seguridad de la información ya que permite una detección y respuesta inmediata, además de ayudar a la recuperación y prevención de futuros ataques.

**Taxonomía**: Clasificación u ordenación en grupos de cosas que tienen características comunes.

En el contexto de la ciberseguridad, la taxonomía de incidentes es muy importante ya que permite agruparlos por características que tengan en común frente a la diversidad y complejidad que tienen los ciberataques, permitiendo así marcar un estandar sobre como tratar cada incidente, evitando que las respuestas de las distintas organizaciones puedan provocar confusiones o malentendidos.

Una taxonomía correcta puede ayudar a:
+ Identificación rapida de los incidentes.
+ Mejor comunicación entre departamentos, organizaciones o países.
+ Realizar una respuesta efectiva.
+ Mayor aprendizaje y mejora.

Crear una taxonomía es bastante complejo, por lo que organismos como en *CCN-CERT* o la *ENISA* ofrecen los suyos. Sin embargo si se quiere elaborar una propia es conveniente tener en cuenta:
+ Tipo de amenaza o método.
+ Origen de la amenaza.
+ Categoría de seguridad de los sistemas afectados.
+ Perfil de los usuarios afectados.
+ Número y tipología de los sistemas afectados.
+ Impacto que el incidente puede tener en la organización.
+ Requerimientos legales y regulatorios.

Clasificación definida en la ***Guía Nacional de Notificación y Gestión de Ciberataques***:
+ Contenido abusivo.
    - SPAM.
    - Delito de odio.
    - Pornografía infantil, contenido sexual o violento inadecuado.
+ Contenido dañino o malicioso.
    - Sistema infectado.
    - Servidor C&C (Mando y Control).
    - Distribución de malware.
    - Configuración de malware.
    - Malware dominio DGA.
+ Obtención de información.
    - Escaneo de redes (scanning).
    - Análisis de paquetes (sniffing).
    - Ingeniería social.
+ Intento de intrusión.
    - Explotación de vulnerabilidades conocidas.
    - Intento de acceso con vulneración de credenciales.
    - Ataque desconocido.
+ Intrusión.
    - Compromiso de cuenta con privilegios.
    - Compromiso de cuenta sin privilegios.
    - Compromiso de aplicaciones.
    - Compromiso de sistemas.
    - Robo.
+ Disponibilidad.
    - DoS.
    - DDoS.
    - Mala configuración.
    - Sabotaje.
    - Interrupciones.
+ Compromiso de la información.
    - Acceso no autorizado a información.
    - Modificación no autorizada de información.
    - Pérdida de datos.
    - Fuga de información confidencial.
+ Fraude.
    - Uso no autorizado de recursos.
    - Derechos de autor.
    - Suplantación de identidad.
    - Phishing.
+ Vulnerable.
    - Criptografía débil.
    - Amplificador DDoS.
    - Servicios con acceso potencial no deseado.
    - Revelación de información.
    - Sistema vulnerable.
+ Otros.
    - APT (Advanced Persistent Threats).
    - Ciberterrorismo.
    - Incidentes relacionados con infraestructuras críticas.
    - Otros.

Otros factores a tener en cuenta:
+ **Grado de gravedad/peligrosidad**: Determina la amenaza que supondría en los sistemas que un incidente ocurriera (1->Bajo, 2->Medio, 3->Alto, 4->Muy alto, 5->Crítico).
+ **Impacto/alcance del incidente**: Las consecuencias que puede tener en la organización que se produzca un incidente (Bajo, Medio, Alto, Muy alto, Crítico).
+ **Prioridad**: Se basa en las 2 anteriores. (Emergencia, Alta, Normal, Baja).

![tabla prioridad](/prioridad.png)

## 2.2.1.-SOC - Servicios y herramientas

Términos:
+ **SOC (Security Operations Center)**: Centro de operaciones de seguridad, que se encarga de la supervisión continua, detección, respuesta y prevención de amenazas. Su enfoque es amplio y abarca todas las operaciones de seguridad. El SOC es el encargado de la seguridad de la organización y abarca todas las operaciones de seguridad.
+ **CERT (Computer Emergency Response Team)**: Equipo especializado en preparar y responder a emergencias de ciberseguridad, como ataques DDoS o ransomware. Suele actuar de manera reactiva ante incidentes.
+ **CIRT (Computer Incident Response Team)**: Similar al CERT, pero centrado en la gestión de incidentes de seguridad específicos, con un enfoque en la contención y erradicación.
+ **CSIRT (Computer Security Incident Response Team)**: Variante más amplia del CIRT, que incluye una visión más estratégica y alineada con las políticas de seguridad.

Objetivos de un SOC:

1. Prevención.
2. Detección.
3. Respuesta.
4. Recuperación.

Los SOC son completamente necesarios a día de hoy debido a la creciente cantidad de amenazas que existen además de que protegen la continuidad del negocio y permite a las empresas operar en entornos digitales de forma segura. Algunos **beneficios** de tener un SOC:

+ Preotección proactiva.
+ Respuesta rápida.
+ Cumplimiento normativo.
+ Confianza del cliente.

Componentes de un SOC:
+ **Servicios**: Son el resultado del trabajo conjunto de personas, procesos y teconologías. Servicios principales:
    - **Threat Intelligence**: se encarga de recopilar y analizar información sobre amenazas externas.
    - **SIEM Intelligence y alerting**: utiliza los datos proporcionados por Threat Intelligence y registros internos para detectar patrones sospechosos en tiempo real.
    - **Monitoring y triage**: actúa como el primer nivel de análisis, revisando las alertas generadas por el SIEM para determinar si representan incidentes reales o falsos positivos.
    - **Incident response**: gestiona incidentes confirmados para contener y mitigar su impacto.
    - **Forensics**: investiga los incidentes para entender cómo ocurrieron, su impacto y cómo prevenir futuros ataques.
    - **Threat hunting**: busca de manera proactiva amenazas avanzadas que no han sido detectadas por las herramientas automáticas del SOC.
    - **Purple team**: evalúa la efectividad del SOC mediante simulaciones de ataques y pruebas de las defensas existentes. 
+ **Tecnologías**: Proporcionan las herramientas necesarias para monitorear, detectar y responder a amenazas. Herramientas según su función:
    - **SIEM**: Recopila y correlaciona datos de múltiples fuentes para identificar eventos de seguridad.
    - **SOAR**: Automatiza tareas de respuesta y orquesta las interacciones entre herramientas del SOC.
    - **Herramientas de Threat Intelligence**: Recopilas información sobre amenazas emergentes y la comparten con el SOC.
    - **Herramientas de monitoreo de red y endpoints**: Supervisan el tráfico de red y las actividades en los dispositivos finales para detectar amenazas.
    - **Herramientas IDS/IPS**: Monitorean y bloquean actividades maliciosas en la red.
    - **Sistemas de ticketing**: Gestionan y documentan los incidentes dentro del SOC.
    - **Tecnologías de análisis forense**: Permiten analizar incidentes después de que han ocurrido.
+ **Procesos**: Guían la gestión de amenazas e incidentes. Estos procesos se diseñan para estandarizar operaciones, reducir el tiempo de respuesta, facilitar la comunicación y promover la mejora continua.
+ **Personas**: Toman decisiones críticas y actúan frente a los incidentes. Algunos roles en un SOC:
    - Gerente del SOC.
    - Analistas SOC.
    - Especialistas de Threat Hunters.
    - Especialistas en Threat Intelligence.
    - Ingenieros de seguridad.
+ **Negocio**

Tipos de estructuras de un SOC:
+ **Organización interna**: Un SOC interno es construido, administrado y operado por la propia organización.
+ **SOC tercerizado**: Es operado por un proveedor externo que ofrece servicios de seguridad gestionados.
+ **Modelos híbridos**: Ciertas funciones del SOC son internas y otras son tercerizadas.

Fases de implementación de un SOC:
+ Negocio --> Definición de objetivos.
+ Personas --> Selección de roles.
+ Procesos --> Definición de flujos de trabajo.
+ Tecnologías --> Selección de herramientas.
+ Servicios --> Definición de servicios iniciales y establecimiento de métricas.

**IOC (Indicador de compromiso)**: Es una pieza de información que puede ser utilizada para detectar actividades malisiosas o sospechosas en una red o sistema. Por ejemlo direcciones IP, URLs y dominios, hashes de archivos...

**MISP** es una plataforma abierta que se utiliza para el intercambio, almacenamiento y correlación de indicadores de compromiso. 

## 2.2.2.-SIEM & Casos de uso

Un **caso de uso** en relación a un SOC es un escenario específico en el que se desccribe cómo detectar, analizar y respondes a amenazas. Estos casos de uso describen las acciones, los eventos, las fuentes de datos y las respuestas que se esperan del personal.

**Pasos** para crear casos de uso:
1. Identificación de amenazas relevantes.
2. Definición del escenario de amenaza.
3. Identificación de fuentes de datos.
4. Definición de indicadores de compromiso.
5. Creación de reglas y alertas.
6. Definición de procedimientos de respuesta.
7. Validación y ajuste.
8. Documentación y capacitación.
9. Monitorización continua y mejora.

**Beneficios** de tener casos de uso definidos:
+ Visibilidad integral.
+ Detección temprana de amenazas.
+ Estandarización y coherencia.
+ Eficiencia de la respuesta.
+ Reducción de falsos positivos.
+ Gestión de riesgos mejorada.
+ Adaptación a amenazas emergentes.
+ Cumplimiento y reporte.

## 2.2.3.-Implantación de un SIEM

**Componentes** o funciones clave:
+ Agregación de datos.
+ Correlación.
+ Notificación.
+ Paneles.
+ Cumplimiento.
+ Retención.
+ Forense.

**Fases** de implementación:
1. **Fase de descubrimiento y planificación**: Establecer una lista de metas y objetivos para clasificarlos según la importancia que tengan para la organización, permitiendo establecer prioridades. Hay que tener en cuenta las políticas, eligiendo cuáles son importantes para el negocio, para el cumplimiento normativo y cuáles se consideran mejores. Implica la implementación de un SIEM.
2. **Fase piloto**: A partir de los datos obtenidos en la etapa anterior probar las suposiciones a las que se ha llegado, ejecutando el SIEM para ello.
3. **Fase de implemetación**: Se desarrolla un flujo de trabajo para realizar la implementación completa del SIEM en la organización, probando el entorno en producción real.
4. **Fase de mejora continua**: Una vez implementado el SIEM se seguirán recogiendo datos sobre su funcionamiento, permitiendo así realizar ajustes. La implementación del SIEM estará en constante cambio.

## 2.2.4.-Evolución de SIEM

Con la existencia de amenazas avanzadas que son capaces de cambiar constantemente su comportamiento, los SIEM deben procesar datos y mejorar para reconocer nuevos patrones en estos.

Un **SIEM** debe evolucionar para procesar un mayor volumen y variedad de datos, mejorar su capacidad de correlación y mejorar la interoperabilidad y las plataformas de inteligencia de amenazas.

**SOAR (Security Orchestration, Automation and Response)**: Se encarga de ayudar a las organizaciones a mejorar la detección y respuesta de amenazas. Esta compuesto por 3 mercados tecnológicos:
+ Orquestación y automatización de la seguridad.
+ Plataformas de respuesta a incidentes de seguridad (SIRP)
+ Plataformas de inteligencia de amenazas (TIP).

Las herramientas SOAR impulsan a las organizaciones a recopilar mayores volúmenes de datos internos/externos y procesarlos de forma más rápida y precisa, permitiendo a los equipos a tomar decisiones rápidas y mejor informadas. Además, está ayudando a estandarizar los procedimientos de respuesta y análisis de incidentes, con el objetivo de automatizar parcial o totalmente una serie de actividades para que el equipo de seguridad pueda centrarse en buscar amenazas.

**Beneficios** de utilizar herramientas SOAR:
+ Automatización de tareas.
+ Automatizar la clasificación básica de seguridad.
+ Liberar a los analistas de seguridad para trabajar en tareas no repetitivas.
+ Lograr la excelencia operacional.

**Obstaculos** sobre el uso de herramientas SOAR:
+ Muchos sistemas SOAR son demasiado caros.
+ Los sistemas SOAR requieren programación, pero la mayoría de los equipos SOC carecen de desarrolladores.
+ Las llamadas integraciones listas para usar son demasiado limitadas.
+ Las API de las herramientas de seguridad son demasiado limitadas.
+ Los SOCs creen que sus procesos son demasiado ad hoc o especializados para ser automatizados.
+ Los SOCs carecen del tiempo necesario para construir y ajustar las automatizaciones por sí solas.

## 2.3.1.-Fuentes Abiertas. OSINT

El *Footprinting* es la técnica encargada de recopilar datos del entorno digital de una organización para identificar vulnerabilidades y puntos de entrada.

Si esta recopilación de datos se realiza a través de fuentes públicas se llama OSINT.

**Usos** de OSINT:
+ Detección de amenazas.
+ Investigaciones forense.
+ Pentesting y hacking ético.
+ Protección de la identidad digital.
+ Vigilancia de la dark web.

**Usos de OSINT en ciberseguridad**:
+ **OSINT en autitoría de seguridad e investigación forense**: Es muy importante ya que permite:
    - Identificar información expuesta que podría ser utilizada por atacantes.
    - Analizar vulnerabilidades en infraestructuras y sistemas sin interacción directa.
    - Obtener evidencias en investigaciones forenses tras un ataque.
+ **OSINT en pentesting y hacking ético**: Permite recopilar información sin escaneos activos que puedan ser detectados. Algunas técnicas:
    - Google Dorking para encontrar documentos sensibles expuestos.
    - Búsqueda en redes sociales para obtener información sobre empleados.
    - Análisis de metadatos en documentos públicos para descubrir información interna.
+ **OSINT en prevención de ataques y detección de amenazas (Threat intelligence)**: Permite monitorear posibles ataques antes de que ocurran. Se encarga de:
    - Detectar filtraciones de datos en la dark web.
    - Analizar grupos de ciberdelincuentes que planean ataques.
    - Monitorear menciones a la empresa en foros de hacking.

**Fases** del ciclo OSINT:
1. **Planificación y dirección**: Se define qué información se necesita y se establecen objetivos.
2. **Identificación de fuentes**: Identificar las fuentes de donde se obtendrá la información.
3. **Adquisición de información**: Se recopila información de forma activa, siendo almacenada para analizarla posteriormente.
4. **Procesamiento y organización**: En esta fase se clasifica la información, se organiza y se eliminan los datos que no sean tan importantes.
5. **Análisis e interpretación**: Se analiza la información, identificando patrones, correlaciones y amenazas potenciales.
6. **Difusión y aplicación de la inteligencia**: La información obtenida se presenta de forma clara a los responsables para que puedan tomar decisiones.

**Técnicas** de OSINT:
+ **Footprinting**: Es el proceso de recopilar información sobre un objetivo (persona, empresa, sistema) sin interactuar directamente con él. Permite entender la infraestructura, tecnologías y servicios utilizados.
+ **Fingerprinting**: Se refiere a la identificación de características específicas de sistemas, dispositivos o usuarios, como versiones de software, sistemas operativos o configuraciones de red.
+ **Google Dorking**: permite encontrar información oculta usando operadores avanzados en Google.
+ **Recopilación de metadatos en documentos**: Exiftool, FOCA, Metagoofil.
+ **Redes sociales**: Sherlock, OSINTgram, Twint.
+ **Dominios y servidores**: WHOIS, NSLookup/Dig, Shodan.
+ **Deep y Dark web**: TOR Browser, OnionScan, DarkSearch.
+ **Análisis de imágenes y videos**: Google Images, TinEye, Exiftool, FotoForensics.

OSINT se basa en la recopilación y alálisis de información de fuentes abiertas, pero su mal uso puede generar problemas legales.

Algunos **principios** sobre un buen uso de OSINT:
+ Respeto a la privacidad.
+ Cumplimiento legal.
+ Propósito legítimo.
+ Fuentes verificadas.
+ Minimización de datos.

## Esquema

![esquemaUD2](/esquema.png)

## Conclusiones personales

De los proyectos que se han realizado durante la unidad el más complejo sin duda ha sido la implementación y configuración de un SIEM, creo que el tutorial o informe que se da de ayuda para la realización de la tarea en poco completo además de estar desactualizado ya que había muchos problemas con las versiones instaladas.
Otros proyectos como el de investigación y desarrollo de una taxonomía de incidientes o el de clasificación de un incidente son interesantes ya que animan a los alumnos a investigar términos, noticias o máquinas comprometidas. 
El proyecto más interesante bajo opinión personal, ha sido el de OSINT, en el que se ha tenido que investigar el hospital de San Rafael y el correo de un compañero. Esto hace que nos demos cuenta de la información que existe de nosotros publicada en internet de forma totalmente pública, pudiendo acceder cualquiera a esta.
En cuanto a las actividades OSINT, sí que me parecen un poco dificil de comenzar sin tener una noción de cómo funcionan las herramientas que quizás puedan ser más complejas.
Al igual que en el resumen de la unidad anterior, creo que todo lo que son conceptos podrían añadirse a una especie de glosario de palabras para así separarlo del resto de la unidad y de la parte práctica que puede ser lo más interesante de realizar.