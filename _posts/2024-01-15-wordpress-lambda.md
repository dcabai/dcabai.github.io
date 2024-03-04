---
layout: single
title:  "¿Wordpress usando funciones Serverless de AWS?"
categories: cloud aws serverless
tags: cloud aws serverless 
date:   2024-01-15 12:50:23 -0400
classes: wide
---
Las arquitecturas serverless han ganado popularidad debido a su capacidad para escalar automáticamente y gestionar la infraestructura de forma transparente, además de su bajísimo costo en comparación con máquinas virtuales. 

En ese sentido se me ocurrió pensar, ¿cómo podríamos correr Wordpress, el CM que más se usa en el mundo, usando sólo funciones Serverless sobre AWS? 

1.  **Creación de una cuenta de AWS:** Si aún no tienes una, regístrate en AWS en aws.amazon.com y configura tu cuenta.
   
2.  **Configurar el VPC:** Todos los servicios que habilitaremos necesitan que se configure un VPC según las mejores prácticas de AWS.

3. **Habilitación de CloudFront:** Necesitamos implementar un cache http para Wordpress. Esto lo hacemos configurando CloudFront. Si no quieres habilitar el cache en las páginas, al menos configúralo para CSS/JS.

4. Necesitamos que le llegue el evento a la función Lambda PHP y para eso podemos configurar el **API Gateway** o una Lambda [Fuction URL](https://docs.aws.amazon.com/lambda/latest/dg/lambda-urls.html). Con la segunda opción podemos conectar el CloudFront hacia Lambda directamente y usar CloudFront para cambiar la URL que nos da AWS.

5. Ahora necesitamos habilitar en **Lambda** un PHP runtime como [Bref](https://github.com/brefphp/bref) y luego el Wordpress como tal.

6. Opcional: usar **ElastiCache** para hacer cache de objetos, pero al habilitarla necesitarás también un **NAT Gateway**.

7. La base de datos por defecto para Wordpress es **MySQL**, podemos usarla en modalidad Serverless también ocupando RDS.

8. Por último, dónde vamos a subir los archivos de imágenes o si nuestro sitio tiene “uploads”? Necesitamos habilitar un **S3**, pero con acceso directo ya que no tenemos un servidor que direccione el tráfico, para esto podemos usar [URL pre firmadas](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html).

9.  **Monitoreo y registro:** Configura **CloudWatch** para monitorear los registros de la función Lambda y la API Gateway. Esto te ayudará a identificar cualquier problema y optimizar el rendimiento de tu sitio Wordpress.
    
10.  **Seguridad:** No puede faltar IAM, Security Hub y Systems Manager para administración y seguridad.

Dejo una arquitectura a alto nivel de qué componentes se requieren habilitar. Voy a estar haciendo el paso a paso en un video para subirlo más adelante. 

![image-center](/assets/images/wordpress-lambda/wordpress-lambda.png){: .align-center} 

Esta arquitectura te proporciona la flexibilidad y la escalabilidad necesarias para manejar cualquier carga de trabajo, sin preocuparte por la infraestructura subyacente. Además, voy a hacer el mismo artículo usando componentes en Azure. Aquí no es exactamente igual porque se usan los App Services pero haremos limonada con los limones que cada nube nos dé.