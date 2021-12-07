---
layout: single
title:  "AWS re:Invent 2021 Recap - Los Anuncios Clave"
categories: aws eventos cloud 
tags: cloud aws multicloud drp vmconaws eventos novedades
date:   2021-12-07 12:50:23 -0400
classes: wide
---
La semana pasada fue el evento anual de Amazon **AWS, re:Invent 2021** donde todos los años comentan los anuncios de nuevos servicios, mejoras y cambios. Este fue el primero que tenía la opción presencial post-pandemia por lo que fue algo especial.

Además, fue el primero de su nuevo CEO, Adam Selipsky entrgando el Keynote del martes, ya que el CEO anterior Andy Jassy pasó a ser el CEO de Amazon en reemplazo de Jeff Bezos.

En general hubo anuncios de interés, pero ninguno se sintió realmente genial e innovador. Pareció más como si Amazon estuviera haciendo el backlog del roadmap de cada producto. Fueron mejoras “incrementales” sobre productos existentes para buscar madurez que entregar servicios innovadores.

> El CTO de Amazon, Werner Vogels, señaló que gran parte de la
> innovación se estaba produciendo detrás de bastidores mientras la
> empresa trabajaba para simplificar las operaciones para sus clientes.

También es el primer re:Invent en mucho tiempo donde AWS no anuncia una nueva base de datos, pero sí movió muchos servicios a serverless y agregó capacidades en otros.

Ahora si, estos son los anuncios que yo considero que vale la pena destacar, hay mas y para la lista completa sugiero ir al link oficial de AWS re:Invent que dejo debajo de todo.

**30 nuevas zonas de AWS en 2022:**

Lo pongo primero porque entre las nuevas zonas están Argentina, Chile y Colombia. Lo que hace que la región pueda crecer muchísimo el año que viene.

**Construct Hub:** [Link](https://aws.amazon.com/blogs/aws/announcing-general-availability-of-construct-hub-and-aws-cloud-development-kit-version-2/)
Un lugar donde podemos encontrar “constructs” o partes de código ya creado para la nube y que podemos reutilizar. Tiene varios lenguajes y está focalizado en la nube. Esto nos ahorra muchísimo tiempo al no tener que reescribir IaC que ya esté hecha.

**AWS Private 5G**: [Link](https://aws.amazon.com/private5g/)
Permitirá construir tu propia red celular 5G privada. Será ideal para casos de uso como una bodega, un campus grande o una mina donde se busca ayudar a aumentar el ancho de banda y la cobertura para los dispositivos mientras se mantiene la seguridad y el control de una red privada.

AWS te envía todo lo que necesitas, incluidas las tarjetas SIM. Y no hay costos iniciales o por dispositivo. Los clientes solo pagan por la capacidad de la red y el rendimiento que se solicita.

**SageMaker Canvas:** [Link](https://aws.amazon.com/blogs/aws/announcing-amazon-sagemaker-canvas-a-visual-no-code-machine-learning-capability-for-business-analysts/)
Esto puede ayudar a generar predicciones de aprendizaje automático mediante una interfaz visual sin código. Esto permite a las personas, como los analistas de negocios, que pueden tener poca o ninguna experiencia en ML, ingresar y obtener información valiosa de los datos.

**Amazon SageMaker Serverless Inference**: es una nueva opción que permite implementar fácilmente modelos de aprendizaje automático para inferencia sin tener que configurar o administrar la infraestructura subyacente. Ideal para aplicaciones con tráfico intermitente o impredecible. Por ejemplo, un servicio de chatbot utilizado por una empresa de procesamiento de nóminas experimenta un aumento en las consultas al final del mes, mientras que durante el resto del mes el tráfico es intermitente.

**SageMaker Studio Lab:** [Link](https://aws.amazon.com/blogs/aws/now-in-preview-amazon-sagemaker-studio-lab-a-free-service-to-learn-and-experiment-with-ml/)
Es gratis, sí empiezo por ahí. Está diseñado para ayudar a cualquier persona a aprender y experimentar con ML sin la necesidad de tener una cuenta de AWS, una tarjeta de crédito o conocimientos de configuración de la nube.

**Amazon WorkSpaces Web:** [Link](https://aws.amazon.com/blogs/desktop-and-application-streaming/announcing-the-general-availability-of-amazon-workspaces-web/)
Un nuevo servicio de VDI donde en vez de darte un desktop completo te entrega una solución de Web Browser en modalidad SaaS para que puedas navegar en los sitios y aplicaciones corporativas en formato Web de forma segura y mas económicamente.

**Amazon DevOps Guru for RDS**: [Link](https://aws.amazon.com/blogs/aws/new-amazon-devops-guru-for-rds-to-detect-diagnose-and-resolve-amazon-aurora-related-issues-using-ml/)
Esta nueva capacidad para DevOps Guru facilita a los desarrolladores la detección, el diagnóstico y la resolución de problemas en Aurora.

**AWS Shield:** [Link](https://aws.amazon.com/blogs/aws/aws-shield-advanced-update-automatic-application-layer-ddos-mitigation/)
Una nueva capacidad llamada Automated Application Layer DDoS Mitigation, la cual permite que AWS Shield genere y despliegue WAF de capa 7 en forma automática en tus aplicaciones, “on behalf”, en caso de detectar un DDoS y poder mitigarlo. Busca automatizar resolver ese problema de seguridad.

**Amazon CodeGuru:**
En este caso agregaron una capacidad nueva para detectar “secretos” en el código fuente o archivos de configuración. Esto pueden ser contraseñas, API keys, SSH key y tokens de acceso.

**AWS Amplify Studio**: [Link](https://aws.amazon.com/about-aws/whats-new/2021/12/aws-amplify-studio/)
Este servicio te ayuda a crear visualmente aplicaciones en horas en lugar de semanas utilizando una interfaz visual que requiere pocos conocimientos sobre cómo escribir código. Podes configurar un backend, crear componentes de interfaz de usuario y conectarlos. #nocode

**Amazon S3 Glacier Instant Retrieval storage class**: [Link](https://aws.amazon.com/blogs/aws/amazon-s3-glacier-is-the-best-place-to-archive-your-data-introducing-the-s3-glacier-instant-retrieval-storage-class/)
Esta nueva clase aprovecha el bajo costo de Glacier pero a su vez con acceso instantáneo el cual es perfecta para casos de uso como archivos multimedia o imágenes médicas.

La clase existente de Amazon S3 Glacier ahora se llama S3 Glacier Flexible Retrieval y ofrece recuperaciones masivas gratuitas en 5 a 12 horas, el cual además bajo su costo un 10%.

**AWS Lake Formation:**
Agregaron nuevas funciones para proporcionar acceso seguro a datos confidenciales en el servicio, con la introducción de capacidades de seguridad a nivel de fila y celda.

**DynamoDB Standard-Infrequent Access table class**: [Link](https://aws.amazon.com/blogs/aws/new-dynamodb-table-class-save-up-to-60-in-your-dynamodb-costs/)
Los clients estaban moviendo datos de acceso infrecuente desde DynamoDB hacia S3 y hacía que tengan aplicaciones y arquitecturas complejas por temas de costo. Así que AWS sacó esta nueva clase que permite aprovechar un ahorro de hasta un 60% en el costo y sin necesidad de sacar la información de DynamoDB hacia otro producto.

**Amazon Inspector**: [Link](https://aws.amazon.com/blogs/aws/improved-automated-vulnerability-management-for-cloud-workloads-with-a-new-amazon-inspector/)
Este servicio se puede utilizar para automatizar la evaluación y la gestión de la seguridad y cumplimiento normativo de las cargas de trabajo implementadas en AWS. La gestión de vulnerabilidades ha cambiado mucho en los últimos seis años, por lo que AWS hizo un “relaunch” de Amazon Inspector desde cero para hacer lo que la gente realmente necesita.

Otros servicios y capacidades anunciadas:

Además anunciaron opciones **Serverless** y bajo demanda para **Redshift**, **EMR**, **MSK** y **Kinesis**
**AWS Cloud WAN**
**IoT Greengrass integrado al Systems Manager**
**Instancias EC2 M1 Mac**
**SageMaker Ground Truth Plus**
**AWS Trainium-based Amazon EC2 Trn1 instances**
**Procesadores Graviton3 para instancias C7g**
**VPC IPAM**
**VPC Network Analyzer**
**IoT ExpressLink**


Como conclusión te cuento que esto es un breve resumen de lo que yo considero fue clave de re:Invent 2021. AWS ahora cuenta con más de 200 servicios, lo que puede causar mucha confusión, pero como dijo por ahí su CEO cuando se lo preguntaron, “no tienes que usarlos todos como si estuvieses recolectando cartas Pokémon, pero lo importante es que están disponibles si los necesitas”.

Link: [AWS Top Announcementes of AWS re:Invent 2021](https://aws.amazon.com/blogs/aws/top-announcements-of-aws-reinvent-2021/)  
Link: [All AWS What’s new in 2021](https://aws.amazon.com/about-aws/whats-new/2021/)