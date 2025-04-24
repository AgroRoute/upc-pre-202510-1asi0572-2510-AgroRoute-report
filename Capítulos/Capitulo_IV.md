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