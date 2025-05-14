# Capítulo IV: Solution Software Design 

Este capítulo presenta el diseño detallado del software, con énfasis en la estructura y el desarrollo de la solución planteada. Se describen las principales decisiones arquitectónicas, la elección de tecnologías y las metodologías de desarrollo empleadas para asegurar que el sistema satisfaga los requisitos establecidos en etapas previas del proyecto. 

## 6.1. Software Configuration Management

En esta sección se explica el método empleado para administrar la configuración del software durante el desarrollo del proyecto. Se registra el uso de herramientas de control de versiones, como Git, para mantener la consistencia del código y fomentar el trabajo colaborativo. Asimismo, se especifican las políticas de gestión de ramas y las estrategias de integración continua (CI/CD) utilizadas para asegurar la estabilidad y la calidad del producto en cada entrega.

 
### 6.1.1. Software Development Environment Configuration

Esta sección describe el entorno de desarrollo utilizado en el proyecto, detallando las herramientas de software implementadas en las distintas etapas del ciclo de vida de la aplicación IoT. A continuación, se presenta cada herramienta junto con su función específica:

**Project Management:**
Se utilizó GitHub como plataforma principal para el control de versiones y almacenamiento de artefactos. Esta herramienta facilitó la colaboración entre los integrantes del equipo mediante el seguimiento de cambios, la creación de ramas y la organización de entregables.

**Product UX/UI Design:**
Para diseñar la experiencia de usuario y mapear los flujos, se emplearon herramientas como Miro y UXPressia, abordando tanto los escenarios actuales (As-Is) como los futuros (To-Be). Figma se utilizó para la creación de prototipos interactivos, wireframes y mockups de la interfaz de usuario.


**Software Development:**

- **Frameworks:** Se eligieron diferentes frameworks de acuerdo con las necesidades de cada componente:
    

- **Angular:** Seleccionado para el desarrollo del frontend, gracias a su versatilidad y capacidad para construir interfaces web dinámicas y responsivas.
    
- **Spring Boot (Java):** Utilizado en el backend por su eficacia en la creación de microservicios robustos y escalables.
    

**Lenguaje de programación:**
El proyecto utilizó una combinación de lenguajes dependiendo del componente:

- **Java:** Lenguaje principal en el backend, por su robustez y escalabilidad.
    
- **C++:** Utilizado en el desarrollo de componentes IoT, dada su eficiencia para el control de hardware.
        
- **TypeScript/JavaScript:** Empleados junto con Angular en la implementación del frontend.

**Control de versiones:**
Se optó por Git como sistema de control de versiones, operado desde la consola para administrar repositorios locales y remotos, permitiendo una colaboración efectiva entre los desarrolladores.

**Software Testing:**
Durante la etapa de testing, se usó Gherkin para definir pruebas de aceptación, las cuales se integraron posteriormente a los pipelines automatizados en GitHub.

**Software Deployment:**
La implementación y gestión de los servicios se realizó en la nube de Google, lo que permitió escalar los recursos y administrar eficientemente la infraestructura.

**Software Documentation:**
Se recurrió a plataformas en línea como Oracle y otras fuentes de referencia para documentar los servicios desarrollados, con el objetivo de facilitar la transferencia de conocimiento y asegurar la mantenibilidad del sistema.

Todas estas herramientas y tecnologías se seleccionaron respetando los lineamientos del proyecto, garantizando una colaboración eficaz y un flujo de trabajo alineado con los objetivos planteados. 

### 6.1.2. Source Code Management

El equipo ha establecido un esquema organizado de control de versiones utilizando la plataforma **GitHub** para el seguimiento de todas las modificaciones del código. Cada producto relacionado con **TransportApp** tendrá su propio repositorio de GitHub, incluyendo la **Landing Page**, los **Web Services**, y las **Frontend Web Applications**. 

![repositories](/resources/images/capitulo_6/repositories.png)

Para la gestión del control de versiones se adoptará el flujo de trabajo GitFlow, fundamentado en el modelo propuesto por Vincent Driessen en su artículo *"A Successful Git Branching Model"*. Este enfoque contempla la utilización de varias ramas además de la principal (main), destacando la rama develop para integrar el desarrollo continuo. Cada nueva funcionalidad se implementará en una rama de características (feature branch) independiente, la cual se incorporará a develop tras su finalización y validación 

**Agro Route Reporte**
![branches](/resources/images/capitulo_6/branches_agro-route_report.png) 

**Agro Route Backend**
![branches](/resources/images/capitulo_6/branches_agro-route_core.png) 

**Agro Route Web**
![branches](/resources/images/capitulo_6/branches_agro-route_web.png) 

**Agro Route Landing**
![branches](/resources/images/capitulo_6/branches_agro-route_landing.png) 

En la administración de versiones de lanzamiento se utilizarán ramas dedicadas, como las release branches y hotfix branches, respetando las convenciones de nomenclatura definidas por el equipo. Las publicaciones del software se regirán por el esquema de Versionado Semántico 2.0.0, lo que garantiza un manejo coherente y claro de las versiones.


**Estructura de Conventional Commits**

Se implementará el estándar **Conventional Commits** para redactar los mensajes de cada commit, con el objetivo de mantener una estructura coherente y estandarizada en los registros del repositorio. Esta práctica contribuirá a una mejor comprensión y seguimiento del historial de cambios por parte de todo el equipo.

A continuación, se muestra el formato que se empleará para los mensajes de commit, incluyendo los tipos más habituales: 

`<type>(<scope>): <subject>`

- **type**: Tipo de commit (feat, fix, docs, etc.)
- **scope**: La parte del proyecto afectada (opcional pero recomendado)
- **subject**: Breve descripción de lo que se realizó

1. **feat**: Se utiliza cuando se agrega una nueva funcionalidad.
    - Ejemplo: `feat(landing): add About Us section to landing page`
2. **fix**: Se utiliza para corregir un error.
    - Ejemplo: `fix(api): resolve bug in authentication service`
3. **docs**: Se usa para cambios en la documentación.
    - Ejemplo: `docs(readme): update repository description`
4. **style**: Cambios relacionados con el formato que no afectan la funcionalidad (espacios en blanco, formato, etc.).
    - Ejemplo: `style(backend): reformat code to meet style guide`
5. **refactor**: Para modificaciones en el código que no corrigen errores ni agregan características, sino que mejoran la estructura.
    - Ejemplo: `refactor(services): simplify service layer logic`
6. **test**: Para agregar o modificar pruebas.
    - Ejemplo: `test(api): add unit tests for login endpoint`
7. **chore**: Cambios que no afectan el código de producción ni los tests (por ejemplo, actualizaciones en las herramientas de construcción o configuración).
    - Ejemplo: `chore(dependencies): update npm packages`

    
### 6.1.3. Source Code Style Guide & Conventions

En la siguiente sección se explicará las convenciones que se utilizaran en el desarrollo del proyecto las cuales se basan en Gherkin Specifications, HTML Style Guide, Code Style Java de IntelliJ y Kotlin Style Conventions.

GHERKIN

Para los archivos de prueba .feature se utilizó el lenguaje Gherkin

- Se utilizó la plantilla de Scenarios Given-When-Then incluyendo el feature y un ejemplo del escenario en una tabla al final.
![Gherkin1](resources/images/capitulo_6/sourceCode1.png)

- Al final de cada uno se brindó un ejemplo de los pasos en una tabla
![gherkin](resources/images/capitulo_6/sourceCode2.png)

HTML Style Guide

Para el desarrollo de archivos .html se siguieron las siguientes convenciones:

- Se utilizó minúsculas para nombrar a los elementos
![Html](resources/images/capitulo_6/sourceCode3.png)

- Todos los elementos tienen sus finalizaciones
![Html](resources/images/capitulo_6/sourceCode4.png)


JAVA

Para los archivos en Java se aplicaron convenciones en el nombramiento de clases y métodos.

- Se utilizó UpperCamelCase para nombrar clases
    
- lowerCamelCase se utilizó para nombrar variables y métodos.
    

### 6.1.4. Software Deployment Configuration

**Azure App Service para el Frontend:**

* **Hosting:**
El frontend, desarrollado con Angular, está desplegado en Azure App Service, que permite la ejecución fluida de aplicaciones web dinámicas. Angular, siendo un framework SPA (Single-Page Application), aprovecha la entrega eficiente de recursos desde Azure, asegurando tiempos de carga rápidos y escalabilidad automática. Azure maneja el balanceo de carga y la administración de recursos para asegurar la alta disponibilidad y rendimiento del frontend.

* **Integraciones:**
La aplicación Angular está integrada con Azure API Management, que gestiona las llamadas API al backend, garantizando la autenticación y seguridad en las transacciones. Además, se utilizan servicios como Azure Application Insights para monitorear el rendimiento de la aplicación, detectar errores y analizar el comportamiento del usuario en tiempo real, lo que permite optimizar la experiencia del usuario.

**GetJar para Mobile Application**

* **Deployment Platform:**
La aplicación móvil está empaquetada utilizando contenedores en Flutter y desplegada para Android e iOS. Se hace uso de servicios como GetJar para la distribución a los usuarios finales.

* **Integraciones:**
La aplicación móvil se conecta a la API a través de llamadas HTTPS, utilizando Azure API Management para gestionar el tráfico y la autenticación de los usuarios. Otras integraciones incluyen la capacidad de notificaciones push utilizando servicios de Firebase Cloud Messaging (FCM).

**Base de Datos**

* **Azure SQL Database:**
Para la gestión de los datos principales de la aplicación (usuarios, servicios, órdenes), se utiliza Azure SQL Database. Este servicio ofrece escalabilidad, alta disponibilidad y recuperación automática de desastres, lo que garantiza la seguridad y persistencia de los datos, y permite un ajuste del rendimiento automático.

* **MySQL IoT Database:**
Se utilizó una base de datos MySQL específica para el almacenamiento de datos generados por los dispositivos IoT. Esta base está optimizada para manejar grandes volúmenes de datos en tiempo real, asegurando una rápida escritura y consulta de los mismos para su procesamiento.

**Azure IoT Edge - IoT Edge & Edge API (IoT Management)**
* **Hosting:**
El servicio de IoT y la API de Edge están desplegados en Azure IoT Edge y Azure Functions, proporcionando un entorno para procesar datos en el borde de la red antes de enviarlos al backend. Esto permite un análisis en tiempo real de los datos recogidos por los sensores de IoT y la ejecución de acciones inmediatas en dispositivos conectados.

* **Integraciones:**
Los datos recogidos por los dispositivos IoT se almacenan en una base de datos MySQL separada para el procesamiento especializado. La API de Edge también envía los resultados a la Web API para su almacenamiento y gestión adicional.

**Web API (Backend)**

* **Azure API Management - Hosting:**
La API principal está desplegada en Azure API Management y ejecuta el backend utilizando Java, empacado dentro de contenedores Docker. Esto proporciona escalabilidad automática y facilita la implementación de actualizaciones sin tiempos de inactividad significativos.

* **Integraciones:**
Se utiliza Azure SQL Database para almacenar datos de aplicación, como la información de usuarios, transacciones y reportes, mientras que Azure Functions maneja tareas como la gestión de dispositivos IoT, integrándose con el IoT Service y el Edge API para monitorear y procesar datos en tiempo real.
