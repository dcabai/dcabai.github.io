---
layout: posts
title:  "AWS re:invent 2020, una Explosión de Novedades"
categories: cloud eventos
tags: cloud aws eventos vmconaws novedades multicloud
date:   2021-01-15 02:50:23 -0400
---

<figure>
  <img src="/assets/images/reinvent2020.png" alt="AWS re:Invent 2020">
</figure>

AWS re:Invent es una conferencia de anuncios y aprendizaje organizada por Amazon Web Services (AWS) para la comunidad global de cloud computing. Con anuncios de apertura, lanzamientos, sesiones y más, el evento AWS re:Invent se llevó a cabo durante 3 semanas, desde el 30 de noviembre hasta el 18 de diciembre. Debido a COVID-19, re:Invent se llevó a cabo virtualmente y fue el evento virtual más grande de AWS, con cientos de sesiones dirigidas por expertos de AWS. En esta publicación voy a resumir algunos de los anuncios que yo considero claves.

## Amazon ECS Anywhere

AWS recibió feedback de los clientes que quieren los mismos métodos de implementación que AWS pero en OnPremise. Para eso anunciaron el lanzamiento de Amazon ECS Anywhere, que permite a los usuarios ejecutar ECS en sus propios Data centers. También se anunció Amazon EKS Anywhere, que permite a los usuarios ejecutar EKS en sus propios Data centers no solo en la infraestructura tradicional administrada por AWS, sino también en la infraestructura administrada por el cliente.

## AWS Lamba Container Support

Los usuarios de Lambda ahora pueden empaquetar e implementar funciones de Lambda como imágenes de contenedor de hasta 10 GB de tamaño. De esta manera, los usuarios también pueden crear e implementar fácilmente cargas de trabajo más grandes como el machine learning.

## Aurora Serverless v2

AWS ha creado Aurora Serverless v2, un modo sin servidor, que permite escalar a cientos de miles de transacciones en una fracción de segundo. La compatibilidad para MySQL ya está lista y PostgreSQL estará disponible en el primer semestre de 2021. Amazon Aurora Serverless v2 también ofrece la gama completa de capacidades de Amazon Aurora, incluida la compatibilidad con Multi-AZ, base de datos global y réplicas de lectura.

## Amazon Elastic Compute Cloud (EC2) Mac

Las instancias EC2 de Mac permiten a los clientes ejecutar cargas de trabajo de macOS bajo demanda en AWS por primera vez, lo que extiende la flexibilidad, escalabilidad y los beneficios de costos de AWS a todos los desarrolladores de Apple.

## VPC Reachability Analyser

VPC Reachability Analyzer es una nueva función que permite a los usuarios de AWS realizar pruebas de conectividad entre recursos en su Virtual Private Cloud (VPC). Los problemas de conectividad se pueden solucionar y diagnosticar rápidamente con solo realizar un análisis de accesibilidad entre un origen y un destino determinados en la red de VPC.

## AWS CodeBuild

Este es un servicio totalmente administrado por AWS que compila el código fuente, ejecuta pruebas y produce paquetes de software que están listos para implementarse. Con CodeBuild, los usuarios no necesitan aprovisionar, administrar y escalar sus propios servidores de compilación.

## AWS Proton

AWS Proton es el primer servicio de implementación totalmente administrado para aplicaciones sin servidor y en contenedores. Los equipos pueden usar AWS Proton para conectar y coordinar todas las diferentes herramientas necesarias para el aprovisionamiento de infraestructura, implementació de código, monitoreo y actualizaciones.

## AWS Systems Manager Fleet Manager

Esta es una nueva experiencia basada en consola que permite a los administradores de sistemas ver y administrar sus flotas de instancias administradas desde una única ubicación, de manera independiente del sistema operativo, sin necesidad de recurrir a conexiones remotas con SSH o RDP. (Los Sysadmin van a amar esta función)

## Amazon DevOps Guru

Es un servicio de operaciones totalmente administrado que facilita a los desarrolladores y operadores mejorar la disponibilidad de las aplicaciones al detectar automáticamente problemas operativos y recomendar soluciones.

## AWS Fault Injection Simulator (FIS)

Este nuevo servicio te ayuda a realizar experimentos controlados en tus cargas de trabajo inyectando fallas y permitiéndote ver qué pasa. Aprenderá cómo reacciona tu sistema a varios tipos de fallas y comprenderá mejor los modos de falla. Se puede comenzar ejecutando experimentos en entornos de preproducción y luego pasar a ejecutarlos como parte de tu flujo de trabajo de CI/CD y, en última instancia, en producción.

En resumen, **AWS re:invent** estuvo lleno de anuncios de novedades, mejoras y no defraudó. Esta es una muy pero muy breve muestra de los anuncios que a mi me llamaron la antención, pero no dejes de revisar toda la lista. Para eso te dejo los links a todos los anuncios del re:invent y al Blog de novedades de AWS, no puedes dejar de visitarlos si eres un interesado en tecnologías cloud.

Todos los anuncios:  [https://aws.amazon.com/new/reinvent/](https://aws.amazon.com/new/reinvent/)

AWS News Blog:  [https://aws.amazon.com/blogs/aws/](https://aws.amazon.com/blogs/aws/)