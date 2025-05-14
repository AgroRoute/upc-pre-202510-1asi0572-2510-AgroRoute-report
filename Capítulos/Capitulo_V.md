# Capítulo V: Solution UX/UI Design
## 5.1. Style Guidelines
### 5.1.1. General Style Guidelines
#### Logo: 
El logo de nuestra aplicación esté asociado al rubro de transporte de productos perecibles <br>

<img src="https://i.postimg.cc/tCxN09nP/agroroute.jpg" width="160" height="160">

#### Lenguaje aplicado:
Considerando las características de nuestro público objetivo y la naturaleza del producto de software, utilizaremos un lenguaje cercano, casual y respetuoso. Esto favorecerá la generación de confianza y cercanía entre los usuarios y nuestra aplicación.
#### Colores
Para el diseño de nuestra aplicación utilizamos como colores predominantes el verde y el azul, ya que transmiten frescura, confianza, profesionalismo y cercanía. Los tonos oscuros en los encabezados aportan solidez y seriedad, mientras que los detalles en rojo y el violeta de los botones añaden dinamismo y energía al diseño. El fondo claro refuerza la limpieza visual, generando una experiencia amigable y accesible para los usuarios.<br>

<img src="https://i.postimg.cc/yY13jBXs/colores.jpg" width="850" height="380">

#### Icons:
El diseño de íconos utiliza un estilo minimalista y lineal, con una paleta de colores vibrantes y específicos para cada categoría. Los íconos principales (temperatura, humedad y GPS) están destacados en colores rojo, azul y verde, respectivamente, lo que facilita su identificación rápida y refuerza su asociación con las funciones que representan. El resto de los íconos, como Dashboard, Envíos, Gestión de alertas, Sensores y Cerrar sesión, usan tonos grises, manteniendo una jerarquía visual clara. El conjunto logra una interfaz intuitiva, moderna y funcional, con un buen equilibrio entre color y simplicidad.<br>

<img src="https://i.postimg.cc/26dMzntp/icon.jpg" width="550" height="380">

#### Typography:
basada en la fuente Poppins en estilo regular, con una escala modular de tamaños. Se presentan diferentes tamaños de texto, desde 61px hasta 10px, acompañados de su valor equivalente en rem, lo que facilita la adaptación a diseños web responsivos. La jerarquía tipográfica se logra mediante variaciones de tamaño, manteniendo coherencia en la familia tipográfica y el peso. Es una referencia útil para establecer los estilos de títulos, subtítulos, párrafos y textos secundarios en una interfaz digital. <br>

<img src="https://i.postimg.cc/0N00jZ9C/Captura-de-pantalla-2025-05-13-135720.jpg" width="450" height="380">

### 5.1.2. Web, Mobile, IoT Style Guidelines

#### Web Style Guidelines
Estas guías definen los estándares visuales y de interacción que deben aplicarse a la interfaz para garantizar una experiencia de usuario simple, clara, accesible y eficiente.

1. **Simplicidad y minimalismo.**  
   La interfaz debe ser limpia, enfocada y sin elementos innecesarios, priorizando la claridad de las acciones principales y utilizando espacios en blanco que faciliten la lectura y la navegación.

2. **Claridad y lenguaje accesible.**  
   Todos los textos deben ser breves, claros y fáciles de entender, evitando tecnicismos y asegurando que botones, íconos y acciones estén correctamente etiquetados para que el usuario comprenda su función sin ambigüedades.

3. **Consistencia visual y funcional.**  
   El diseño debe mantener coherencia en colores, tipografía, iconografía y disposición de elementos en todas las secciones, evitando cambios bruscos o desorientadores para que la experiencia de navegación sea uniforme y predecible.

4. **Acciones seguras y reversibles.**  
   Las acciones críticas, como eliminar o modificar registros, deben contar con confirmaciones y permitir deshacerlas cuando sea posible, evitando consecuencias irreversibles o errores no intencionados por parte del usuario.

5. **Feedback inmediato al usuario.**  
   Toda acción realizada debe generar una respuesta visual o textual que confirme su ejecución, ya sea mediante cambios de color, íconos de validación o mensajes de estado que informen sobre el resultado de la operación.

6. **Diseño responsivo y accesible.**  
   La interfaz debe adaptarse correctamente a diferentes dispositivos y tamaños de pantalla, asegurando legibilidad y funcionalidad, además de cumplir con estándares de contraste y accesibilidad para usuarios con diversas capacidades.

#### Componentes:

Componentes de los botones que se han usado <br> 

<img src="https://i.postimg.cc/85hfV7K3/componentes.jpg" width="550" height="380">

Componentes en los formularios <br>

<img src="https://i.postimg.cc/SsK3B9xQ/comp.jpg" width="550" height="380">

Tipografía:
La tipografía para utilizar es importante para la aplicación móvil. El que consideramos a utilizar, se basa en la siguiente imagen para que el usuario se sienta cómodo con la lectura de la información brindada.<br>
<img src="https://i.postimg.cc/0N00jZ9C/Captura-de-pantalla-2025-05-13-135720.jpg" width="450" height="380">

#### IoT Style Guidelines
- **Privacidad y Transparencia**  
  Los datos generados por dispositivos IoT deben ser recopilados, transmitidos, procesados y utilizados únicamente con fines justificados y claramente definidos. En este proyecto, el propósito es monitorear la ubicación de las encomiendas enviadas. La información recopilada debe estar disponible únicamente para el cliente que posea el código de seguimiento correspondiente, garantizando así la privacidad y confidencialidad de los datos.

- **Gestión de Datos**  
  Los datos provenientes de dispositivos IoT deben ser validados y verificados utilizando tanto datos en tiempo real como históricos. Es fundamental implementar un sistema de control de versiones para distinguir entre datos originales y actualizados. Asimismo, deben definirse políticas claras para la retención y eliminación de datos, especialmente de las copias maestras, con el fin de mantener integridad y trazabilidad.

- **Infraestructura**  
  Para facilitar la coordinación a nivel nacional de las implementaciones IoT, las entidades responsables deben mantener un inventario actualizado de los dispositivos IoT desplegados, utilizando formatos estandarizados. Este inventario debe incluir tanto los dispositivos como los activos (públicos o privados) donde se encuentren instalados, así como las redes utilizadas para su operación.

- **Seguridad**  
  Los sistemas IoT deben diseñarse con un enfoque proactivo en la seguridad, minimizando riesgos como accesos no autorizados, ciberataques, fallas operativas, manipulación de datos y amenazas ambientales. Se deben adoptar marcos de seguridad reconocidos siempre que sea posible, asegurando que la comunicación entre componentes esté debidamente restringida.  
  Todos los datos deben estar protegidos tanto en tránsito como en reposo. Además, los sistemas deben estar blindados contra accesos no autorizados, y los dispositivos no deben contar con interfaces vulnerables (por ejemplo, puertos USB inseguros) ni permitir la extracción sencilla de mecanismos de almacenamiento.

- **Operación y Sostenibilidad**  
  Toda nueva implementación de dispositivos o soluciones IoT debe estar respaldada por una necesidad justificada, un caso de negocio sólido y un beneficio público comprobable (económico, social o ambiental). Antes del despliegue a gran escala, debe realizarse una prueba de concepto.  
  Las soluciones implementadas deben ser monitoreadas mediante métricas de desempeño claras. Los acuerdos contractuales deben establecer los resultados esperados, niveles de servicio y prever acciones correctivas (incluyendo sanciones o cancelaciones) en caso de incumplimiento.

## 5.2. Information Architecture
### 5.2.1. Organization Systems

En AgroRoute, el sistema de organización visual se centrará en estructurar la información de manera clara y accesible. Utilizando principios como la proximidad, los datos relacionados, como las alertas de temperatura, humedad y ubicación de los productos, se agruparán de forma que cada conjunto de información se mantenga cercano a su categoría correspondiente, facilitando la consulta rápida. La organización jerárquica de fuentes será clave, donde los títulos principales de las secciones, como "Estado de Ruta" o "Alertas Activas", se destacarán con un tamaño de fuente mayor y mayor peso, mientras que los detalles más específicos se mostrarán con un estilo más liviano para facilitar la lectura. Además, el contenido será categorizado según audiencia (transportistas, empresas logísticas, administradores) y tópicos, como rutas disponibles, condiciones de los vehículos, y productos monitoreados, para garantizar una navegación eficiente. El esquema cronológico se aplicará en la visualización de las rutas y estados de transporte, permitiendo ver las actualizaciones más recientes en la parte superior de la pantalla, mientras que la información histórica se presentará de manera ordenada, para facilitar el seguimiento de las rutas anteriores.

### 5.2.2. Labeling Systems

A continuación, se definirán las etiquetas a utilizar para agrupar conjuntos de información, así como las asociaciones entre las mismas.

#### Landing Page:

Inicio -> Nosotros -> Soluciones -> Contáctanos

<img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/organization.png?raw=true">

### 5.2.3. SEO Tags and Meta Tags

#### Landing Page:

Title:

``` <title>AgroRoute</title> ```

Meta Tags Description:

``` <meta name="keywords" content="monitoreo perecibles, transporte alimentos, cadena de frío, IoT logística, sensores temperatura"/> ```

Keywords:

``` <meta name="description" content="AgroRoute - Monitoreo inteligente de productos perecibles durante el transporte con tecnología IoT. Control de temperatura, humedad y ubicación en tiempo real."/> ```

Authors:

``` <meta name="author" content="AgroRoute Team"/> ``` 

### 5.2.4. Searching Systems

El sistema de búsqueda de AgroRoute permitirá visualizar en tiempo real el estado de las rutas de transporte de productos perecibles, mostrando datos clave como temperatura, humedad y ubicación de los productos. Se podrá buscar por tipo de vehículo, conocer las condiciones específicas de la carga, y recibir alertas instantáneas en caso de cualquier desviación de los parámetros óptimos. Además, el sistema ofrecerá filtros para visualizar las rutas más cercanas, las alertas activas, y la disponibilidad de sensores, garantizando una trazabilidad total y la eficiencia del transporte en la cadena de frío.

### 5.2.5. Navigation Systems

Se dispondrá de un menú desplegable en la parte superior de la página de la aplicación, el cual mostrará las secciones de contenido disponibles.
El “navbar” permitirá al usuario poder navegar a cualquier sección de la página, en cualquier momento, esto permitirá a los usuarios ver todo el contenido sin tener que volver al principio y cuando sea necesario, con un botón, volver a desplegar el navbar de manera incluso más sencilla en web dirigiéndose al menú directamente.

## 5.3. Landing Page UI Design
### 5.3.1. Landing Page Wireframe 

<div align="center">

#### 1 Sección del Landing Page:
<img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/wir1.png?raw=true">

#### 2 Sección del Landing Page:
<img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/wir2.png?raw=true">

#### 3 Sección del Landing Page:
<img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/wir3.png?raw=true">

</div>

### 5.3.2. Landing Page Mock-up

#### 1 Sección del Landing Page:

<div align="center">
  <img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/flow1.png?raw=true">
  
  #### Flow 1
  
  <img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/flow2.png?raw=true">

  #### Flow 2
  
  <img src="https://github.com/AgroRoute/upc-pre-202510-1asi0572-2510-AgroRoute-report/blob/feature/capitulo-5/resources/images/flow3.png?raw=true">

  #### Flow 3
</div>

## 5.4. Applications UX/UI Design
### 5.4.1. Applications Wireframes

#### Aplicación web:
<img src="https://i.postimg.cc/cJS3H7ph/wiref1.jpg">
<img src="https://i.postimg.cc/135tYC1L/wiref2.jpg">
<img src="https://i.postimg.cc/Ls9zbwVw/wiref3.jpg">
<img src="https://i.postimg.cc/9F2zbTbN/wiref4.jpg">
<img src="https://i.postimg.cc/FHcW4M3K/wiref5.jpg">

#### Aplicación mobile:
<img src="https://i.postimg.cc/QMvcdCDG/mobil1.jpg">
<img src="https://i.postimg.cc/B6MsCLnR/mobil2.jpg">
<img src="https://i.postimg.cc/BnH0VwvT/mobile3.jpg">

### 5.4.2. Applications Wireflow Diagrams

A continuación, se presentan los wireflows respectivos a nuestros user goals.

User goal 1: Dado a que el usuario desea crear una cuenta, se presentan los pasos que debe seguir el usuario para registrarse en la aplicación. <br>

<img src="https://i.postimg.cc/VNfQ7qH4/11.jpg">

User goal 2: Dado a que el usuario desea iniciar sesión, se presentan los pasos que debe seguir el usuario para iniciar sesión en la aplicación. <br>

<img src="https://i.postimg.cc/xdZQcktR/12.jpg">

User goal 3: Dado a que el usuario se encuentra en el dashboard de la aplicación, desea registrar un envío para que sea monitoreado. <br>

<img src="https://i.postimg.cc/4dvWjq79/13.jpg">

User goal 4: Dado a que el usuario se encuentra en la pantalla de envíos, desea monitorear la temperatura y humedad sus productos de su envío. <br>

<img src="https://i.postimg.cc/zvZy6DHJ/14.jpg">

User goal 5: Dado a que el usuario se encuentra en la  pantalla de envíos, desea monitorear la ruta del transportista en tiempo real mediante un mapa. <br>

<img src="https://i.postimg.cc/L86nrb5Z/15.jpg">

User goal 6: Dado a que el usuario se encuentra en la  pantalla de gestión de alertas, desea visualizar las alertas de sus productos, como niveles altos de la temperatura o humedad. <br>

<img src="https://i.postimg.cc/3wzN0rBg/16.jpg">

User goal 7: Dado a que el usuario se encuentra en la  pantalla de sensores, desea visualizar los sensores activos y su ultima hora de actualización de la temperatura, humedad y GPS. <br>

<img src="https://i.postimg.cc/c4dHnbQ5/17.jpg">

### 5.4.3. Applications Mockups
### 5.4.4. Applications User Flow Diagrams
## 5.5. Applications Prototyping
