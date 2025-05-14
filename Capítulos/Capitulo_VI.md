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


Esta sección detalla las convenciones que se emplearán en el desarrollo del proyecto, basándose en las especificaciones de Gherkin, las guías de estilo de HTML, y las convenciones de estilo de código para Java e IntelliJ y Kotlin.

**GHERKIN**

Para los archivos de prueba con extensión `.feature`, se usará el lenguaje Gherkin.

- Se deben usar escenarios con el formato **Given-When-Then**, incluyendo un título de feature y un ejemplo escrito en este formato con sangrías para mejorar la legibilidad. Se sugiere comenzar cada paso con “And” cuando sea parte del mismo bloque.

```gherkin
Scenario: Discernible Given-When-Then Blocks
  In order to quickly spot where one block ends and another one begins,
  you can indent the steps starting with “And”

  Given I need to prepare some data for my scenario
    And this is more complex so I need a second step
    And this is more complex so I need a third step

  When I trigger some action
    And I can see this outcome
    And this outcome also has a second step
    And this outcome also has a third step
```

- Al final de cada escenario, se incluirá un ejemplo en forma de tabla para mostrar los datos utilizados. Es importante dejar líneas en blanco entre pasos para evitar confusión, especialmente cuando se usan tablas.

```gherkin
Scenario Outline: Newline before Examples
  Squashed together steps with no newlines to separate them
  makes it more difficult to discern which information belongs together
  especially if tables are involved

  Given I add a new person
    And this person has the birthdate `<birthdate>`

  When I try to save this person

  Then I receive the error message for `invalid birthdate`

  Examples:
    | birthdate |
    | 01.01.1800 |
```

**HTML Style Guide**

Para archivos `.html`, se deben seguir estas normas:

- Los nombres de los elementos deben escribirse en minúscula.

```html
<body>
  <p>This is a paragraph.</p>
</body>
```

- Todos los elementos deben cerrarse correctamente.

```html
<section>
  <p>This is a paragraph.</p>
</section>
```

**JAVA**

Para los archivos en Java:

- Se emplea el formato **UpperCamelCase** para nombrar clases y métodos.
- Se utiliza **lowerCamelCase** para nombrar variables y atributos.


### 6.1.4. Software Deployment Configuration

**Google Cloud Provider Compute Engine para el Frontend**

* **Hosting:**  
El frontend, desarrollado con Angular, se despliega en usando una instancia de Google Cloud Provider (GCP), lo que facilita la ejecución de aplicaciones web dinámicas.

* **Integraciones:**  
Las llamadas al backend son hechas desde la misma instancia GCP que aloja el frontend de la aplicación. También se emplea el dashboard brindado por GCP para supervisar el rendimiento, registrar errores y analizar la interacción del usuario en tiempo real, mejorando así la experiencia del usuario.


**Bases de Datos**

* **MySQL Database:**  
Se emplea esta base de datos para almacenar información crítica de la aplicación como usuarios, servicios y órdenes. Ofrece escalabilidad, alta disponibilidad y recuperación automática ante fallos, lo que garantiza la seguridad de los datos y un rendimiento ajustable automáticamente.

* **Base de Datos MySQL para IoT:**  
Se utiliza una instancia específica de MySQL para capturar y procesar datos generados por dispositivos IoT. Esta base está optimizada para manejar grandes volúmenes de datos en tiempo real, asegurando velocidad tanto en escritura como en lectura.

**Web API (Backend)**

* **Google Cloud Provider Compute Engine - Hosting:**
La API principal se despliega usando una instancia de GCP Management utilizando backend en Java, empacado en contenedores Docker. Esto permite escalar automáticamente y aplicar actualizaciones sin afectar la disponibilidad del sistema.

* **Integraciones:**  
Los datos relacionados con usuarios, transacciones y reportes se almacenan en una base de datos MySQL.