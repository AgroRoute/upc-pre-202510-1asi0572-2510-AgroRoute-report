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

