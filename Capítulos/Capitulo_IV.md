## 4.1.1.2 Domain Message Flows Modeling
    
#### Evento: Transport Request

Este evento se dispara cuando un cliente inicia sesión y registra una solicitud de transporte en la plataforma AgroRoute. En esta etapa, se especifican los detalles críticos del envío: tipo de mercancía, peso, dimensiones y condiciones ambientales (temperatura, humedad).

![Sticky Note Packs](/resources/images/capitulo_4/Event_Transport_Petition.png)

#### Evento: Transport Alert

Durante el transporte, los sensores IoT monitorean temperatura, humedad y ubicación. Se envían alertas si se detectan desviaciones de los parámetros establecidos, garantizando que la mercancía se conserve en condiciones óptimas.

![Sticky Note Packs](/resources/images/capitulo_4/Event_Transport_Alert.png)

## 4.1.1.3 Bounded Contexts Canvases
---
#### Client Management

Este contexto se encarga de toda la interacción con los usuarios de la plataforma. Aquí ocurren procesos como el registro, inicio de sesión, autenticación y manejo de perfiles. Es esencial porque garantiza que solo personas autorizadas puedan acceder y gestionar información delicada del transporte. También permite diferenciar entre tipos de usuarios (como empresas o particulares), y sirve como punto de entrada para todo el ecosistema AgroRoute.


![cd](/resources/images/capitulo_4/1_Client_Management_Context.png)
#### Shipment Request

Aquí se capturan todos los datos necesarios para crear una solicitud de transporte. El cliente indica desde dónde se enviará la mercancía, a dónde debe llegar, qué tipo de productos se transportan y bajo qué condiciones (temperatura, humedad, etc.). Este contexto valida la solicitud y la prepara para ser gestionada por otros componentes, como la asignación de transportistas. Es donde comienza la cadena logística en AgroRoute.

![cd](/resources/images/capitulo_4/2_Shipment_Request_Context.png)

#### Carrier Assignment

Este contexto toma las solicitudes de transporte y busca transportistas disponibles que puedan cumplir con los requerimientos del envío. Considera disponibilidad horaria, rutas posibles y si el vehículo tiene los sensores y controles necesarios (como refrigeración). Aquí se decide quién será el encargado de mover la carga. Es vital para asegurar la calidad del servicio y la puntualidad en la entrega.

![df](/resources/images/capitulo_4/3_Carrier_Assignment_Context.png)

#### Real Time Monitoring

Durante el viaje, este contexto se activa para recoger datos de sensores IoT que miden variables como temperatura, humedad o ubicación. Si algo se desvía de lo permitido, se generan alertas automáticas para que el cliente o el operador tomen acción inmediata. Este es el corazón de AgroRoute en términos de valor diferencial: asegurar que la carga llegue en buen estado mediante monitoreo constante.

![df](/resources/images/capitulo_4/4_Real_Time_Monitoring_Context.png)

#### Service Tracking and Reporting

Después de completado el transporte, este contexto permite visualizar lo que ocurrió: si hubo incidentes, cómo fue el comportamiento ambiental durante el trayecto y si se respetaron los parámetros establecidos. También se generan reportes históricos que el cliente puede consultar o descargar. Es útil para auditar servicios, tomar decisiones futuras y cumplir con normativas de calidad.

![df](/resources/images/capitulo_4/5_Service_Tracking_and_Reporting_Context.png)

---

## 4.2 Tactical-Level Domain-Driven Design

A continuación se definen, para cada Bounded Context, las responsabilidades y la funcionalidad de sus capas, así como los fragmentos de código necesarios para generar los diagramas de componentes, de clases y de base de datos.


### 4.2.1. Bounded Context: Device Management
Se encarga de registrar, configurar y mantener el estado de los dispositivos IoT de la plataforma (sensores de temperatura/humedad y rastreadores GPS), así como de exponer su operativa básica.

#### 4.2.1.1. Domain Layer
Contiene el modelo de dominio puro:
- **IoTDevice**: entidad padre que abstrae atributos comunes (identificador, serial, estado).
- **TemperatureHumiditySensor**: especialización para lecturas de temperatura y humedad.
- **LocationTracker**: especialización para lecturas de posición geográfica.
- **AnomalyDetectionService**: servicio de dominio que compara lecturas contra umbrales y genera eventos de alerta.

#### 4.2.1.2. Interface Layer
Define los puntos de entrada de la capa de presentación:
- **TemperatureHumiditySensorController**: expone endpoints REST para registrar sensores y enviar lecturas.
- **LocationTrackerController**: expone endpoints REST para registrar rastreadores y enviar coordenadas.
- **AnomalyAlertController**: permite consultar y reenviar alertas generadas por el servicio de dominio.

#### 4.2.1.3. Application Layer
Orquesta los casos de uso de Device Management:
- **TemperatureHumiditySensorCommandHandler**: valida peticiones de lecturas y delega en el dominio.
- **LocationTrackerCommandHandler**: valida peticiones de ubicación y delega en el dominio.
- **AlertNotificationHandler**: gestiona el envío de notificaciones tras la detección de anomalías.

#### 4.2.1.4. Infrastructure Layer
Contiene los mecanismos técnicos para respaldar los casos de uso:
- **TemperatureHumiditySensorApplicationService**: coordina la persistencia de lecturas de sensores.
- **LocationTrackerApplicationService**: coordina la persistencia de lecturas de GPS.
- **AlertService**: implementa la lógica de notificación a terceros.
- **IoTDeviceRepository**: mantiene la información de dispositivos en la base de datos.
- **SensorRepository**: repositorio especializado que filtra dispositivos por tipo.

#### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams
![cd](/resources/images/capitulo_4/BC_DeviceManagement.jpg)

#### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams
![cd](/resources/images/capitulo_4/BC_DeviceManagement_Class.png)

##### 4.2.1.6.2. Bounded Context Database Design Diagram
![cd](/resources/images/capitulo_4/BC_DeviceManagement_DB.png)

*Descripción:* Sensor-specific tables heredan la PK de `iot_device` para centralizar estado y configuración.

---

### 4.2.2. Bounded Context: Telemetry Ingestion
Recibe, valida y normaliza en tiempo real los datos transmitidos por los dispositivos IoT.

#### 4.2.2.1. Domain Layer
- **TelemetryRecord**: entidad que representa una lectura genérica (timestamp, deviceId, payload).
- **ReadingValidator**: servicio de dominio que asegura integridad y formato de datos.

#### 4.2.2.2. Interface Layer
- **TelemetrySubscriber**: adaptador MQTT que suscribe topics de dispositivos.
- **TelemetryRestController**: endpoint HTTP para ingestión de respaldo.

#### 4.2.2.3. Application Layer
- **IngestTelemetryHandler**: coordina validación y persistencia de lecturas.

#### 4.2.2.4. Infrastructure Layer
- **TelemetryApplicationService**: implementa casos de uso de ingestión.
- **TelemetryRepository**: persiste `TelemetryRecord` en almacenamiento.

#### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams
![cd](/resources/images/capitulo_4/BC_TelemetryIngestion.png)

#### 4.2.2.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.2.6.1. Bounded Context Domain Layer Class Diagrams
![cd](/resources/images/capitulo_4/BC_TelemetryIngestion_Class.png)

##### 4.2.2.6.2. Bounded Context Database Design Diagram
![cd](/resources/images/capitulo_4/BC_TelemetryIngestion_DB.png)

*Descripción:* Tabla única de lecturas que almacena datos brutos para normalización posterior.

---

### 4.2.3. Bounded Context: Anomaly Detection & Alerting
Define políticas para evaluar lecturas y notificar a las empresas transportistas ante condiciones críticas.

#### 4.2.3.1. Domain Layer
- **Alert**: entidad que registra un evento crítico (tipo, dispositivo, timestamp, detalles).
- **AlertPolicy**: configuración de umbrales por parámetro.
- **AnomalyDetector**: servicio de dominio que genera instancias de `Alert`.

#### 4.2.3.2. Interface Layer
- **AlertController**: expone endpoints para consultar, confirmar o descartar alertas.

#### 4.2.3.3. Application Layer
- **DetectAnomalyHandler**: recibe lecturas, invoca `AnomalyDetector`, persiste alertas y dispara notificaciones.

#### 4.2.3.4. Infrastructure Layer
- **AlertService**: implementa notificaciones push, correo y webhooks.
- **AlertRepository**: persiste `Alert` y políticas en la base de datos.

#### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams
![cd](/resources/images/capitulo_4/BC_AnomalyDetectionAlerting.png)

#### 4.2.3.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.3.6.1. Bounded Context Domain Layer Class Diagrams
![cd](/resources/images/capitulo_4/BC_AnomalyDetectionAlerting_Class.png)
##### 4.2.3.6.2. Bounded Context Database Design Diagram
![cd](/resources/images/capitulo_4/BC_AnomalyDetectionAlerting_DB.png)
*Descripción:* `alert` almacena eventos críticos; `alert_policy` define umbrales configurables.

---

### 4.2.4. Bounded Context: User & Access Control
Administra la autenticación, autorización y perfiles de las empresas transportistas.

#### 4.2.4.1. Domain Layer
- **User**: entidad que representa una cuenta de empresa.
- **Role**: valor que define permisos (ADMIN, USER).
- **AuthService**: servicio de dominio que valida credenciales y emite tokens.

#### 4.2.4.2. Interface Layer
- **AuthController**: endpoints para login, logout y renovación de tokens.
- **UserController**: CRUD de usuarios y asignación de roles.

#### 4.2.4.3. Application Layer
- **LoginHandler**, **RegisterUserHandler**, **AssignRoleHandler**: orquestan casos de uso de usuario.

#### 4.2.4.4. Infrastructure Layer
- **UserService**: lógica de negocio para usuarios.
- **UserRepository**, **RoleRepository**: persistencia de usuarios y roles.

#### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams
![cd](/resources/images/capitulo_4/BC_UserAccessControl.png)

#### 4.2.4.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.4.6.1. Bounded Context Domain Layer Class Diagrams
![cd](/resources/images/capitulo_4/BC_UserAccessControl_Class.png)
##### 4.2.4.6.2. Bounded Context Database Design Diagram
![cd](/resources/images/capitulo_4/BC_UserAccessControl_DB.png)

*Descripción:* gestión de usuarios con roles mediante tabla intermedia.

---

### 4.2.5. Bounded Context: Monitoring & Reporting
Proporciona dashboards, mapas y generación de reportes históricos y en tiempo real.

#### 4.2.5.1. Domain Layer
- **ReportDefinition**: entidad que describe parámetros de generación de informe.
- **DashboardView**: VO que agrupa métricas y configuraciones de vista.

#### 4.2.5.2. Interface Layer
- **DashboardController**: endpoints para mostrar paneles en web y móvil.
- **ReportController**: endpoints para solicitar y descargar reportes.

#### 4.2.5.3. Application Layer
- **FetchDashboardDataHandler**: orquesta lectura de datos agregados.
- **GenerateReportHandler**: genera archivos (PDF/CSV) de informes.

#### 4.2.5.4. Infrastructure Layer
- **ReportingService**: implementa la generación y envío de reportes.
- **ReportRepository**: persiste `ReportDefinition`.
- **QueryViews**: vistas materializadas o tablas de agregación para velocidad.

#### 4.2.5.5. Bounded Context Software Architecture Component Level Diagrams
![cd](/resources/images/capitulo_4/BC_MonitoringReporting.png)

#### 4.2.5.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.5.6.1. Bounded Context Domain Layer Class Diagrams
![cd](/resources/images/capitulo_4/BC_MonitoringReporting_Class.png)

##### 4.2.5.6.2. Bounded Context Database Design Diagram
![cd](/resources/images/capitulo_4/BC_MonitoringReporting_DB.png)

*Descripción:* `report_definition` guarda configuraciones y `vw_dashboard_metrics` acelera consultas de KPI.

---