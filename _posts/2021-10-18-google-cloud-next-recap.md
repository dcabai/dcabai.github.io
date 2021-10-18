---
layout: single
title:  "Google Cloud Next ’21 – Recap"
categories: eventos cloud kubernetes gcp
tags: cloud gcp google kubernetes hybridcloud multicloud eventos
date:   2021-10-18 12:50:23 -0400
classes: wide
---
Ahora es el turno de Google, con su evento anual de anuncios donde la semana pasada, este gigante de la nube y los datos llegó con grandes novedades para destacar y que merecen ser comentados.

En cuanto a su estrategia y visión, vemos que integra mucho mas el mundo multi-cloud, se acerca mas al mundo OnPrem y como siempre, los datos, la analítica y el desarrollo están de la mano de la compañía. Entre los anuncios puedo destacar los siguientes, pero no fueron los únicos:

**Google Distributed Cloud:** Similar a lo que había hecho Microsoft con Azure Stack y AWS con Outpost, ahora Google se suma a la pelea con esta solución de hardware y software totalmente administrado que lleva la infraestructura y los servicios de Google Cloud al Edge y los datacenters de los clientes. Es ideal para ejecutar procesamiento de datos local, cargas de trabajo de extrema baja latencia, ejecutar cargas de trabajo sensibles que cumplan con requisitos normativos o implementar soluciones privadas 5G/LTE para los clientes. [Link](https://cloud.google.com/blog/topics/hybrid-cloud/announcing-google-distributed-cloud-edge-and-hosted)

**BigQuery Omni (for Cross cloud Analytics):** Esto permitirá usar BigQuery a través de otras nubes como por ejemplo AWS y Azure. Tendrá una conexión segura hacia datos en S3 y Blob sin necesidad de estar moviendo data entre nubes. Es una solución realmente diferenciadora de otros hyperscalers pensando en un verdadero mundo multi-cloud.

**Spark on Google Cloud**: Es el primer servicio Spark serverless gestionado en la nube que tiene autoscaling. Esto permitirá a los clientes escalar infinitamente sin importar si empiezan en BigQuery, Dataproc, Dataplex o Vertex AI.

**Vertex AI Workbench:** Es el entorno único para que los científicos de datos completen todo el trabajo de ML, desde la experimentación hasta la implementación, la gestión y el seguimiento de modelos. Se trata de una infraestructura informática totalmente gestionada, escalable y preparada para empresas, basada en Jupyter, con controles de seguridad y funciones de gestión de usuarios. [Link](https://cloud.google.com/vertex-ai-workbench)

**Data Analytics Integrations**: Se anunciaron algunas integraciones con varios productos del mercado para analítica e inteligencia artificial como Collibra, Databricks, Tableu, DRYiCE, Fivetran, etc.

**Google Cloud Cortex Framework:** Este Framework es una base de contenido y plantillas de referencia de soluciones para que los clientes aceleren el time-to-market con menos riesgo, complejidad y costo. Por ahora está disponible para SAP. [Link](https://cloud.google.com/blog/products/sap-google-cloud/faster-time-to-value-with-the-google-cloud-cortex-framework)

**Anthos for Virtual Machines:** Para los clientes con entornos VMware activos, podrán conectar sus VM’s al plano de control de Anthos. Alternativamente, Anthos para VM permitirá mover las VM’s AS-IS a Anthos con KubeVirt, una API de virtualización de código abierto para Kubernetes. [Link](https://cloud.google.com/blog/topics/hybrid-cloud/introducing-anthos-for-vms-and-other-app-modernization-tools)

**Anthos for multicloud:** A través de la nueva API Anthos Multi-Cloud podrán provisionar y gestionar clusters GKE en AWS y Azure.

**Cloud Build Hybrid:** Basado en el CI/CD framework open-source Kubernetes-nativo Tekton, te permitirá construir, probar e implementar cross Cloud y OnPrem, entregando los beneficios de un sistema gestionado por Google sin control-plane para administrar todos los pipelines en todos los entornos.

**Managed Service for Prometheus:** Basicamente Prometheus como servicio gestionado por Google para usar las herramientas que ya tengas o desees usar con compatibilidad de alertas, workflows y dashboards de Graphana existentes.

**Log Analytics:** Hace que los logs de sistema y de los workloads que se ingesten en Cloud Logging estén disponibles para almacenar, administrar y analizar con BigQuery.

**BeyondCorp Enterprise:** Mas características a la solución de zero-trust de Google donde ahora podrán agregar aplicaciones legacy no-Google Cloud y facilidad en la operación y administración gracias a Machine Learning. [Link](https://cloud.google.com/blog/products/identity-security/introducing-beyondcorp-enterprise)

**Automatic DLP:** Es una capacidad revolucionaria que descubre y clasifica datos confidenciales para todos los proyectos de BigQuery en toda la organización sin hacer nada. Con información valiosa por cada tabla y columna, se podrá administrar mejor el riesgo de los datos.

**Serverless**: Varias mejoras en capacidades y características donde desde Cloud Run pueden usar Java Spring Boot, ASP.NET, mayor tiempo de ejecución, etc.

Otras mejoras o funciones adicionales dentro de Cloud Armor, GKE, Apigee, Cloud Build, Cloud NAT, Google Workspace, etc

Para resumir, un player de nube que está posicionado fuertemente en el área Datos con BigQuery, ML, analítica y desarrollo de aplicaciones que se va acercando a los entornos multi-nube y OnPrem para tomar algunos clientes y casos que hasta el momento no podía. A tener mucho ojo porque vamos a ver mas de Google Cloud en el futuro.