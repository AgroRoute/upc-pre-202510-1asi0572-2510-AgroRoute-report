<div align="center"> 

<strong>Universidad Peruana de Ciencias Aplicadas</strong>   
  
<img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/UPC_logo_transparente.png" alt="UPC"> 

<strong>Ingeniería de Software</strong> 
   
<p><strong>Desarrollo de Soluciones IoT</strong></p> 
<p><strong>Profesor: </strong>León Baca, Marco Antonio</p> 
<p><strong>Ciclo: </strong>2025-1</p> 
<p><strong>Sección: </strong></p> 
 
</div> 



--- 

<div align="center">

## Informe de Trabajo Final

#### Team Members 

| Integrantes                          | Código       |
|--------------------------------------|--------------|
| Balceda Calixto, Jenny A.            | U20201B507   |
| Branco Alberto Villegas Peralta      | U20201C082   |
| De la Cruz Arellano, Diego           | U20201C334   |
| Martinez Carbajal, Mariela           | U20211C254   |
| Tasayco Vilcamiza, Damaris           | U202119605   |
 
#### Abril,2025
</div>



<p align="right">(<a href="">Tabla de contenidos</a>)</p>

### 2.3.3. User Journey Mapping

![UserJourneyMapping](https://github.com/AgroRoute/upc-pre-202501-2939-2510-AgroRoute-report/blob/feature/cap%C3%ADtulo-2-UserJourneyMapping/resources/images/User%20Journey%20Map.png?raw=true)

### 2.3.4. Empathy Mapping

![EmpathyMapping](https://github.com/AgroRoute/upc-pre-202501-2939-2510-AgroRoute-report/blob/feature/cap%C3%ADtulo-2-UserJourneyMapping/resources/images/Emphaty.png?raw=true)

### 2.3.5. As-is Scenario Mapping

![Asis](https://github.com/AgroRoute/upc-pre-202501-2939-2510-AgroRoute-report/blob/feature/cap%C3%ADtulo-2-UserJourneyMapping/resources/images/asis.png?raw=true)

## 2.4. Ubiquitous Language


| **Término**               | **Definición**                                                                                                 |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| **Sistema IoT de Monitoreo** (IoT Monitoring System)  | Plataforma que permite la captura, procesamiento y análisis de datos en tiempo real provenientes de sensores instalados en los vehículos de transporte. |
| **Sensores** (Sensors)              | Dispositivos instalados en los vehículos y/o contenedores que miden variables como temperatura, humedad y ubicación de la carga, enviando estos datos a la plataforma IoT. |
| **Paquete Perecible** (Perishable Package) | Cualquier tipo de carga que es sensible a condiciones ambientales como temperatura, humedad, etc., y que puede deteriorarse si no se transporta adecuadamente. |
| **Transportista** (Carrier)        | Persona o empresa responsable de mover el paquete desde un origen hasta un destino, utilizando vehículos que pueden estar equipados con sensores IoT. |
| **Condiciones Críticas** (Critical Conditions)      | Variables (como temperatura y humedad) que deben mantenerse dentro de ciertos parámetros para asegurar la calidad y seguridad del paquete perecible. |
| **Anomalía** (Anomaly)             | Cualquier evento que cause que las condiciones críticas se salgan de los parámetros establecidos, como un aumento de temperatura o una baja de humedad. |
| **Alerta** (Alert)                 | Notificación enviada automáticamente por la plataforma IoT cuando se detecta una anomalía, informando a los responsables de la carga (empresa de transporte, operadores, etc.). |
| **Plataforma IoT** (IoT Platform)  | El software que procesa, analiza y visualiza los datos enviados por los sensores. Permite gestionar las alertas y el monitoreo en tiempo real. |
| **Reacción Correctiva** (Corrective Action) | Acciones tomadas por el transportista o equipo logístico para corregir una anomalía, como ajustar la temperatura o cambiar la ruta del transporte. |
| **Rango de Temperatura/Humedad** (Temperature/Humidity Range) | Parámetros específicos (como 4-8°C para temperatura) dentro de los cuales los productos perecibles deben mantenerse para evitar daños. |
| **Ruta de Transporte** (Transport Route)          | El trayecto que sigue el vehículo de transporte para entregar el paquete, especificado de antemano por la empresa de logística. |
| **Unidad de Frío** (Refrigeration Unit)            | Sistema de refrigeración en el vehículo o contenedor que asegura que la carga perecible se mantenga en las condiciones óptimas durante el transporte. |
| **Empresa de Transporte** (Transport Company)     | Compañía encargada de gestionar y realizar el transporte de los productos perecibles, incluyendo la planificación de la ruta, la asignación de vehículos y la reacción ante alertas. |
| **Responsable Logístico** (Logistics Manager)      | Persona encargada de coordinar el transporte de la carga, verificar las alertas del sistema y tomar decisiones relacionadas con el manejo de las anomalías. |
| **Desviación de Ruta** (Route Deviation)           | Cambio de la ruta originalmente planificada para evitar una anomalía o condición que pueda poner en riesgo la carga (por ejemplo, un accidente o un desvío por mal tiempo). |

# REQUIREMENTS SPECIFICATION

## 3.1. To Be Scenario Mapping

![tobe](https://github.com/AgroRoute/upc-pre-202501-2939-2510-AgroRoute-report/blob/feature/cap%C3%ADtulo-2-UserJourneyMapping/resources/images/tobe.png?raw=true)

## 3.2 User Stories

Para elaborar user stories que pertenecen a un epic. A continuación, las epics que consideramos como equipo:


| **Epic ID** | **Código**        | **Título**                                      | **Epic**                                                                                              |
|-------------|-------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| 1           | EPIC-001          | Monitoreo continuo de condiciones críticas      | Mejorar la visibilidad del transporte de productos perecibles mediante la monitorización continua de variables críticas como temperatura, humedad y ubicación.  |
| 2           | EPIC-002          | Detección temprana y alerta de anomalías        | Implementar un sistema predictivo y de detección temprana de anomalías, como cambios de temperatura o humedad, que permitan tomar decisiones oportunas para evitar daños. |
| 3           | EPIC-003          | Integración y comunicación con responsables     | Desarrollar una comunicación eficiente entre el sistema de monitoreo IoT y la empresa responsable del transporte para facilitar la toma de decisiones rápidas ante anomalías. |
| 4           | EPIC-004          | Reportes y análisis de condiciones de transporte | Proporcionar reportes automáticos y análisis detallados sobre las condiciones del transporte, permitiendo un monitoreo histórico y la mejora continua de los procesos. |
| 5           | EPIC-005          | Optimización proactiva del transporte            | Ofrecer recomendaciones proactivas para optimizar las condiciones de transporte (por ejemplo, ajustar la temperatura, humedad o sugerir cambios de ruta basados en el monitoreo en tiempo real). |



A continuación, se presenta las user stories en el formato de ‘Como-quiero-para’ y los criterios de aceptación en el formato de ‘Dado-cuando-entonces’.


| User Story ID | Título                                       | Descripción (Como, Quiero, Para)                                                                                      | Criterios de Aceptación                                                                                                                                                     | Epic ID |
|---------------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|
| US-001        | Monitoreo de temperatura en tiempo real      | Como empresa de transporte, quiero monitorear la temperatura en tiempo real de los productos perecibles para asegurar que se mantengan en condiciones óptimas. | Escenario: El sistema recibe los datos de temperatura del vehículo. Dado que el sistema está activo, cuando la temperatura se detecta, entonces el sistema actualiza el estado en tiempo real. | 1       |
| US-002        | Monitoreo de humedad en tiempo real          | Como empresa de transporte, quiero monitorear la humedad en tiempo real para evitar que se afecten los productos sensibles a humedad. | Escenario: El sistema recibe los datos de humedad del vehículo. Dado que el sensor de humedad está activo, cuando se recibe el dato, entonces se muestra la lectura actualizada. | 1       |
| US-003        | Posicionamiento geográfico en tiempo real    | Como empresa de transporte, quiero conocer la ubicación geográfica en tiempo real de la carga para asegurar que el paquete está en la ruta correcta. | Escenario: El sistema recibe la señal de ubicación del vehículo. Dado que la ubicación está activa, cuando el sistema obtiene la ubicación, entonces se muestra en el mapa. | 1       |
| US-004        | Alerta temprana por anomalía de temperatura  | Como empresa de transporte, quiero recibir alertas tempranas de cualquier anomalía en la temperatura para prevenir daños en los productos perecibles. | Escenario: El sistema detecta un cambio en la temperatura fuera del rango esperado. Dado que el sistema monitorea constantemente, cuando se detecta una anomalía, entonces se envía la alerta. | 2       |
| US-005        | Alerta temprana por anomalía de humedad      | Como empresa de transporte, quiero recibir alertas tempranas sobre anomalías en la humedad para corregir la condición antes de que afecte los productos. | Escenario: El sistema detecta una anomalía en la humedad. Dado que el sistema está monitoreando constantemente, cuando se detecta una anomalía, entonces se envía la alerta correspondiente. | 2       |
| US-006        | Predicción de anomalías en el trayecto       | Como empresa de transporte, quiero que el sistema prediga anomalías en el trayecto para poder tomar decisiones preventivas y evitar problemas durante el transporte. | Escenario: El sistema realiza un análisis predictivo de los datos históricos. Dado que el sistema tiene los datos previos, cuando se realiza la predicción, entonces se muestra la alerta preventiva. | 2       |
| US-007        | Reacción automatizada por anomalía           | Como empresa de transporte, quiero que el sistema sugiera acciones automáticas cuando detecte anomalías para reducir el tiempo de respuesta y minimizar el riesgo. | Escenario: El sistema detecta una anomalía. Dado que el sistema ha identificado un problema, cuando se detecta la anomalía, entonces el sistema envía una sugerencia de acción correctiva. | 3       |
| US-008        | Sugerencia de acción correctiva              | Como empresa de transporte, quiero que el sistema sugiera qué hacer para corregir las anomalías detectadas, como cambiar la temperatura o ajustar la ruta. | Escenario: El sistema genera una recomendación de acción. Dado que el sistema ha detectado la anomalía, cuando la recomendación se genera, entonces se muestra al responsable. | 3       |
| US-009        | Confirmación de acción tomada                | Como empresa de transporte, quiero confirmar que las acciones correctivas sugeridas han sido ejecutadas para asegurar que el problema se resolvió. | Escenario: El sistema solicita confirmación de acción. Dado que se ha ejecutado la acción, cuando el transportista confirma, entonces el sistema marca la tarea como completada. | 3       |
| US-010        | Gestión de alertas por anomalías             | Como empresa de transporte, quiero gestionar las alertas recibidas para tomar decisiones más informadas sobre el estado de la carga. | Escenario: El sistema envía varias alertas. Dado que el sistema ha detectado anomalías, cuando el responsable revisa las alertas, entonces el sistema muestra el resumen de cada una. | 4       |
| US-011        | Análisis detallado de alertas                | Como empresa de transporte, quiero un análisis detallado de cada alerta para entender mejor las causas y el impacto de las anomalías. | Escenario: El sistema proporciona un análisis detallado. Dado que se detectó una anomalía, cuando se genera el análisis, entonces se muestra una descripción detallada de la alerta. | 4       |
| US-012        | Visualización de alertas en dashboard        | Como empresa de transporte, quiero ver todas las alertas en un solo dashboard para tener una visión clara del estado de todos los envíos. | Escenario: El sistema muestra las alertas en el dashboard. Dado que el sistema ha generado múltiples alertas, cuando se accede al dashboard, entonces se muestran las alertas de forma ordenada. | 4       |
| US-013        | Optimización automática de la ruta           | Como empresa de transporte, quiero que el sistema sugiera automáticamente una nueva ruta si detecta que hay condiciones que pueden afectar el transporte. | Escenario: El sistema detecta un obstáculo en la ruta. Dado que el sistema tiene acceso a mapas en tiempo real, cuando se identifica un problema, entonces se sugiere una nueva ruta. | 5       |
| US-014        | Recalculo de la ruta por anomalía            | Como empresa de transporte, quiero que el sistema recalcule automáticamente la ruta si se presenta una anomalía, como un desvío o tráfico pesado. | Escenario: El sistema detecta una anomalía en la ruta. Dado que el sistema tiene acceso a condiciones de tráfico, cuando se detecta el problema, entonces se recalcula la ruta en tiempo real. | 5       |
| US-015        | Actualización en tiempo real de la ruta      | Como empresa de transporte, quiero que la ruta de transporte se actualice en tiempo real para asegurar que el paquete llegue de manera eficiente. | Escenario: El sistema actualiza la ruta en función de las condiciones de tráfico. Dado que el sistema tiene acceso a mapas en tiempo real, cuando el tráfico cambia, entonces se actualiza la ruta. | 5       |
| US-016        | Notificación de cambios de ruta              | Como empresa de transporte, quiero recibir una notificación cuando haya un cambio en la ruta para poder ajustarme y tomar decisiones oportunas. | Escenario: El sistema genera una notificación. Dado que hay un cambio en la ruta, cuando la actualización es realizada, entonces el sistema notifica al transportista. | 5       |
| US-017        | Integración con otros sistemas logísticos    | Como empresa de transporte, quiero integrar el sistema IoT con otros sistemas logísticos para optimizar todo el proceso de transporte. | Escenario: El sistema se comunica con otros sistemas. Dado que se ha realizado una integración, cuando se recibe la información, entonces se sincroniza con los otros sistemas de gestión. | 1       |
| US-018        | Validación de datos por sensores             | Como empresa de transporte, quiero verificar que los datos enviados por los sensores sean correctos antes de tomar decisiones importantes. | Escenario: El sistema recibe datos de los sensores. Dado que el sistema ha recibido los datos, cuando se procesan, entonces se validan las lecturas antes de ser enviadas. | 1       |
| US-019        | Verificación de la integridad del sensor     | Como empresa de transporte, quiero verificar la integridad de los sensores para asegurarme de que los datos que recibo son fiables. | Escenario: El sistema verifica los sensores. Dado que el sistema realiza una verificación, cuando se realiza la prueba, entonces se informa sobre la condición de cada sensor. | 1       |
| US-020        | Control de temperatura en diferentes puntos  | Como empresa de transporte, quiero poder controlar la temperatura de la carga en diferentes puntos del vehículo para asegurar que el paquete esté siempre en condiciones óptimas. | Escenario: El sistema recibe los datos de temperatura de distintos puntos del vehículo. Dado que el sistema tiene múltiples sensores, cuando se actualizan, entonces se muestra la lectura completa. | 1       |
