# Solar Business

## Descripcion

Solar Business es una plataforma orientada a la gestión y proyección de soluciones de energía solar para clientes residenciales y empresariales. Su objetivo principal es simular costos y ahorros a largo plazo frente al consumo energético tradicional, ofreciendo herramientas de análisis financiero, impacto ambiental y opciones de financiación.

Además, integra un sistema de monitoreo remoto de consumo y generación mediante gateways conectados a inversores solares, garantizando la transmisión segura y confiable de datos en tiempo real.
El despliegue de la solución se realiza en la nube de AWS, con alta disponibilidad, escalabilidad automática y servicios de soporte para garantizar rendimiento, seguridad y experiencia de usuario óptima.

## Roadmap del sprint

<a href="https://github.com/orgs/Solar-Business/projects/2">
  <img src="https://img.shields.io/badge/Sprint-Roadmap-green"/>

</a>

## Link de acta de reunion

-  [ACTA 1 | 20 agosto 2025](https://docs.google.com/document/d/1l-FFlfC3MnyJuHP9edjqS0MlZKIGpHhVreaT1SQ3Yh0/edit?tab=t.u4qlr5qp4fby)
- [ACTA 2 | 27 de agosto 2025](https://docs.google.com/document/d/1l-FFlfC3MnyJuHP9edjqS0MlZKIGpHhVreaT1SQ3Yh0/edit?tab=t.speti09oo53q)

- [ACTA 3 | 5 de septiembre 2025](https://docs.google.com/document/d/1l-FFlfC3MnyJuHP9edjqS0MlZKIGpHhVreaT1SQ3Yh0/edit?tab=t.qb6zy7k2ldcg)

## Documentos

- [Diagrama de bloques](https://drive.google.com/file/d/14ifDsEG5BGkfK7ki_c6epfK5MdmucFpF/view?usp=sharing)

-![diagrama de software](https://www.mermaidchart.com/app/projects/0239e292-861e-4aba-b394-e2cc5811835f/diagrams/499fd2f5-89ef-4dc0-91b7-08bac9b5de69/share/invite/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkb2N1bWVudElEIjoiNDk5ZmQyZjUtODllZi00ZGMwLTkxYjctMDhiYWM5YjVkZTY5IiwiYWNjZXNzIjoiRWRpdCIsImlhdCI6MTc1ODI4NDQ3Nn0.aPoZnAmwDPp9KIhW4UDtVcsl6_yy5mr_-GXEzCJCHps)

## Requerimientos

### Funcionales
#### Sistema:
- RF01: El sistema debe permitir a los usuarios ingresar su consumo mensual de energía en kWh.


- RF02: El sistema debe simular el costo del consumo energético proyectado a 25 años con proveedor actual.


- RF03: El sistema debe simular el ahorro estimado con un sistema de energía solar.


- RF04: El sistema debe generar un reporte visual y comprensible de la comparación entre ambas opciones.


- RF05: El sistema debe almacenar la información del cliente para seguimiento.


- RF06: El sistema debe enviar informes anuales al cliente sobre su ahorro real e impacto ambiental.


- RF07: El sistema debe permitir agendar visitas técnicas personalizadas.


- RF08: El sistema debe ofrecer opciones de financiación y mostrar su impacto en la inversión.


- RF09: El sistema debe conectarse a servicios de monitoreo remoto de consumo y generación.


- RF10: El sistema debe contar con un panel de control para el equipo de soporte técnico.
-
#### Transmisión de datos:

- RF11: El gateway debe recibir datos del inversor (potencia, voltaje, corriente, temperatura).

- RF12:. El gateway debe transmitir la información a un servidor central mediante protocolos estándar (ej. MQTT, Modbus TCP, HTTP).

- RF13:  El gateway debe almacenar datos localmente en caso de pérdida de conexión.

- RF14: El gateway debe sincronizar los datos con el servidor una vez restablecida la red.

- RF15:  El gateway debe permitir comunicación bidireccional, para recibir configuraciones o comandos remotos.

- RF16: El gateway debe registrar y reportar alarmas/fallos del inversor.

- RF17: El gateway debe proveer acceso seguro de usuarios (por ejemplo, autenticación).

#### Despliegue:

- RF18: El sistema debe estar desplegado en instancias EC2 con balanceo de carga mediante un Application Load Balancer (ALB).

- RF19: El sistema debe escalar automáticamente entre 2 y 4 instancias EC2 según la carga de trabajo.

- RF20: El sistema debe enviar notificaciones por correo electrónico al administrador cuando el uso de CPU supere el umbral definido o haya 

#### instancias no saludables.

- RF21: El sistema debe ejecutar un backend Node.js conectado a una base de datos MySQL en Amazon RDS.

- RF22: El sistema debe inicializar automáticamente la base de datos MySQL en el primer despliegue.

- RF23: El sistema debe garantizar que la base de datos RDS solo sea accesible desde las instancias de la aplicación dentro de la VPC.

- RF24: El sistema debe generar un endpoint público (URL) accesible desde el ALB para la aplicación web.

- RF25: El sistema debe mantener la base de datos en subredes privadas, no accesibles desde internet.

- RF26: El sistema debe crear un tópico SNS para centralizar las notificaciones y suscripciones del sistema.

- RF27: El sistema debe registrar logs de ejecución de la aplicación backend en los servidores EC2.

### No funcionales 

- RNF01: La plataforma debe estar disponible 99% del tiempo (alta disponibilidad).


- RNF02: El simulador debe responder en menos de 5 segundos por consulta.


- RNF03: Los datos del usuario deben estar protegidos y cumplir con la ley de protección de datos.


- RNF04: El sistema debe ser responsive y funcionar en móviles, tabletas y computadoras.


- RNF05: El sistema debe ser escalable para soportar aumento de usuarios y servicios.


- RNF06: El diseño debe ser intuitivo y amigable para usuarios no técnicos.

#### Transmisión de datos:

- RFN07: Confiabilidad: 99,9% de disponibilidad de la comunicación.

- RFN08: Seguridad: cifrado TLS/SSL en la transmisión de datos.

- RFN09: Compatibilidad: soportar estándares industriales como RS-485/Modbus y protocolos IP.

- RFN10: Rendimiento: latencia de transmisión menor a 1 segundo en condiciones normales.

- RFN11:  Robustez: tolerancia a fallos eléctricos (picos de voltaje, microcortes).

- RFN12:Usabilidad: interfaz sencilla para instaladores y técnicos.

Despliegue en nube:
- RNF13: El sistema debe desplegarse en Amazon Web Services (AWS) garantizando redundancia geográfica (mínimo en 2 zonas de disponibilidad).

- RNF14: El sistema debe utilizar AWS Elastic Beanstalk, ECS o EKS para la gestión automática de la infraestructura y escalabilidad.

- RNF15: Las bases de datos deben alojarse en Amazon RDS o DynamoDB, con respaldos automáticos diarios y retención mínima de 30 días.

- RNF16: El sistema debe usar AWS IAM para la gestión de roles y permisos, garantizando acceso seguro y segregado.

- RNF17: Se debe habilitar un CDN (Amazon CloudFront) para optimizar la entrega de contenidos estáticos a nivel global.

- RNF18: El despliegue debe integrarse con un pipeline de CI/CD en AWS CodePipeline para automatizar actualizaciones y despliegues.

## Grupo de trabajo - Roles
> - Samuel Barona -  Developer
> - Sebastian Guerrero - Developer
> - Alexis Jaramillo - Developer
> - Juan Manuel Velosa - Product owner
> - Felipe Velasco - SCRUM master