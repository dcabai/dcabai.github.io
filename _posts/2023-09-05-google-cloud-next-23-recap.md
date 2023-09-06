---
layout: single
title:  "Google Cloud Next 2023 - Recap"
categories: gcp eventos cloud kubernetes
tags: cloud gcp kubernetes hybridcloud multicloud eventos ia novedades 
date:   2023-09-05 12:50:23 -0400
classes: wide
---

![image-center](/assets/images/google-next23/recap.png){: .align-center}

Es tiempo de otro “recap” en este caso el de Google que fue la semana pasada. Estos días se vienen varios eventos de tecnología importantes y todos con grandes anuncios.

En Google Cloud Next 2023, la IA generativa tuvo su protagonismo absoluto. Así como habíamos comentado de ediciones anteriores y en otras tecnologías, la IA está recibiendo todas las miradas. 

Al igual que VMware, en mi artículo anterior, Google Cloud también formó una asociación con NVIDIA para sus GPU y otras herramientas y servicios de inteligencia artificial. En la conferencia anterior Google I/O 2023, la compañía presentó PaLM 2, actualizó Bard y anunció la búsqueda integrada con IA, Android Studio, Play Store, Workspace, Maps y otras cosas más.

> Como empresa, llevamos algún tiempo preparándonos para este momento. Y durante los últimos siete años, hemos adoptado un enfoque que da prioridad a la IA, aplicándola para hacer que nuestros productos sean radicalmente más útiles.
> *-Sundar Pichai (CEO de Google)*

Lo que dice el CEO de Google en esas líneas es: La IA va a ser parte de todo lo que hagamos a partir de ahora. Dentro de todos los anuncios, estos son los que a mi parecer son los más destacados.

**Vertex AI**

La plataforma de unified machine learning (ML) de Google, recibió un gran update. Algunas incorporaciones más recientes incluyen Code Llama y Llama 2 de Meta, Falcon LLM del Technology Innovation Institute y Claude 2 de Anthropic. Google Cloud también actualizó modelos desarrollados internamente, como PaLM, para permitir resultados de mayor calidad.

También presenta búsqueda de múltiples turnos, que permite a los usuarios hacer preguntas de follow-up y una funcionalidad de resumen.

Link: [Vertex AI](https://cloud.google.com/vertex-ai)  

**SynthID**

Google Cloud también anunció una nueva funcionalidad de marca de agua digital para Imagen impulsada por SynthID de Google DeepMind. Esto convierte a Google Cloud en el primer proveedor de nube a hiperescala que permite la creación de marcas de agua invisibles y resistentes a manipulaciones en imágenes generadas por IA. Es una tecnología de última generación que incorpora la marca de agua digital directamente en la imagen de píxeles, haciéndola invisible para el ojo humano y muy difícil de alterar, sin dañar la imagen.

Link: [Google DeepMind](https://www.deepmind.com/synthid)  

**Duet AI**

Tras la introducción de Duet AI en Workspace, ahora presenta Duet AI en Google Cloud. Duet AI funcionará como un desarrollador experto, un SRE, un DBA, un analista de datos experto y un asesor de ciberseguridad. Sólo le falta barrer el data center. Básicamente será lo que Jarvis era para Iron Man, pero en este caso para nuestras cargas en la nube.

Es una clara respuesta a Microsoft 365 Copilot, que básicamente es el mismo “concepto”. Tendremos que ver cuál tiene las mejores respuestas a las necesidades del mundo real.

Aquí te detallo en qué nos puede ayudar en cada campo de operación:

- **Desarrollo de Software**: brinda asistencia experta durante todo el ciclo de vida del desarrollo, lo que permite a los desarrolladores a ser más productivos. Además de completar y generar código, puede ayudar con la refactorización de código y la creación de API mediante indicaciones simples en lenguaje natural.
  
- **Operación de Infraestructura**: Los operadores pueden chatear con Duet AI en lenguaje natural a través de una serie de servicios directamente en Google Cloud Console, para recuperar rápidamente información práctica sobre la configuración de la infraestructura, las mejores prácticas de implementación y recomendaciones de expertos sobre optimización de costos y rendimiento.
  
- **Analítica de Datos**: Duet AI en BigQuery brinda asistencia contextual para escribir consultas SQL y código Python, genera funciones y bloques de código completos, sugiere automáticamente terminaciones de código, explica declaraciones SQL en lenguaje natural y puede generar recomendaciones basadas en tu esquema y metadata.

- **Modernización de Bases de Datos**: Duet AI en Cloud Spanner, AlloyDB y Cloud SQL ayuda a generar código para estructurar, modificar o consultar datos utilizando lenguaje natural. Duet AI en el Database Migration Service proporciona conversión de código asistida por IA para automatizar la conversión de última milla del código de la base de datos de Oracle a PostgreSQL. Además, con soporte para Oracle con Cloud SQL para PostgreSQL como destino. Siempre es bueno saber cómo salir de Oracle.

- **Operaciones de Seguridad**: también se integrará a los productos de seguridad como Chronicle Security Operations, Mandiant Threat Intelligence y Security Command Center, que pueden capacitar a los profesionales de seguridad para prevenir amenazas de manera más eficiente, reducir el trabajo duro en los flujos de trabajo de seguridad y mejorar el talento en seguridad.

Link: [Duet AI in Google Cloud](https://cloud.google.com/duet-ai)  

**Duet AI in Workspace**

Las mejoras para Duet AI en Google Meet harán que la herramienta tome notas durante las videollamadas, envíe resúmenes de reuniones e incluso traduzca subtítulos a 18 idiomas automáticamente. 

Los usuarios podrán chatear directamente con Duet AI para hacer preguntas sobre el contenido, obtener un resumen de los documentos compartidos en un espacio e incluso ponerse al día con las conversaciones perdidas. Google también actualizó la interfaz de usuario y mejoró la búsqueda para permitir a los usuarios estar al tanto de las conversaciones.

Muy similares a las características que habíamos visto en Microsoft Copilot, como mencioné antes, tendremos que ver quién lo incorpora mejor en el día a día, pero sin duda es un gran aporte de ambos gigantes para los usuarios finales.

<iframe width="560" height="315" src="https://www.youtube.com/embed/6DaJVZBXETE?si=WlqIQsDfPoNbRfBF" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>  
<br/>

Link: [Duet AI in Workspace](https://workspace.google.com/solutions/ai/)  

**Cross-Cloud Network**

Google presentó la red Cross-Cloud para permitir una conectividad segura y fluida entre las nubes y las ubicaciones locales. La plataforma de red permitiría a las organizaciones crear aplicaciones distribuidas y ofrecer aplicaciones orientadas a Internet.

Link: [Cross-Cloud Network](https://cloud.google.com/solutions/cross-cloud-network)  

**Cloud Firewall Plus**

Como lo mencionan ellos, el primer cloud next-generation firewall. (NGFW) 

Link:[Cloud Firewall Plus](https://cloud.google.com/firewall)  

**Google Cloud-NVIDIA partnership**

El partnership que lo está cambiando todo, lo vimos con Microsoft, con VMware y ahora con Google y seguramente lo veremos en el evento de AWS más cerca de fin de año. NVIDIA se encuentra entre las pocas empresas que han podido capitalizar el enorme potencial del desarrollo impulsado por la IA.

> La IA generativa está revolucionando cada capa de la pila informática. Nuestras dos empresas cuentan con dos de los equipos de ciencias informáticas más talentosos del mundo para reinventar la infraestructura de la nube para la IA generativa.
> *-Jensen Huang (CEO de NVIDIA)*

> Estamos en una era completamente nueva de transformación digital, impulsada por la inteligencia artificial. Esta tecnología ya está mejorando la forma en que operan las empresas y cómo los humanos interactúan entre sí. Está cambiando la forma en que los médicos atienden a los pacientes, la forma en que las personas se comunican e incluso la forma en que se mantiene a los trabajadores seguros en el trabajo. Y esto es sólo el principio.
> *-Thomas Kurian (CEO de Google Cloud)*
  
Link: [Google Cloud and NVIDIA Expand Partnership to Advance AI Computing, Software and Services](https://nvidianews.nvidia.com/news/google-cloud-and-nvidia-expand-partnership-to-advance-ai-computing-software-and-services)  

**Search Generative Experience (SGE)**

SGE utiliza IA avanzada en la búsqueda de información para que uno pueda comprender un tema más rápido, descubrir puntos de vista, conocimiento o incluso ayudarte a hacer las cosas más fácilmente como, por ejemplo, comprar un artículo que te interesa. Sin ir más lejos, es una mezcla entre Google Search y ChatGPT.

Link: [Supercharging Search with generative AI](https://blog.google/products/search/generative-ai-search/)  

**BigQuery Studio**

Es una interfaz única para ingeniería de datos, análisis y análisis predictivo, ayuda a aumentar la eficiencia de los equipos de datos.

Link: [Announcing BigQuery Studio — a collaborative analytics workspace to accelerate data-to-AI workflows](https://cloud.google.com/blog/products/data-analytics/announcing-bigquery-studio)  

**AlloyDB AI**

Como parte integral de AlloyDB, el servicio de base de datos compatible con PostgreSQL, AlloyDB AI ofrece un conjunto integrado de capacidades para crear fácilmente aplicaciones GenAI, incluidas consultas vectoriales y de alto rendimiento.

Link: [AlloyDB AI](https://cloud.google.com/alloydb/ai)  

Otros anuncios están relacionados con mejorar la **Google Distributed Cloud** con IA, los **Cloud tensor processing units** (TPU) v5e y **máquinas virtuales A3** que incorporan GPU de NVIDA para mejorar el procesamiento de este tipo.

### Conclusión:

Google está aprovechando al máximo el poder de la IA, no sólo en las herramientas de usuario final, sino también en la Google Cloud. Cada anuncio en el evento mostró como aprovechaba la inteligencia artificial para crear una experiencia de usuario más inmersiva y eficiente. El Duet AI es algo que hay que estar mirando, porque el “asistente” de IA es lo que se viene en todas las plataformas grandes de tecnología. Estos son los anuncios que a mi me llamaron la atención, pero te invito a que revises los enlaces de abajo con todo el detalle. 

Link: [All 161 things we announced at Google Cloud Next ‘23 – a recap](https://cloud.google.com/blog/topics/google-cloud-next/next-2023-wrap-up)  
Link: [Watch the best of Google Cloud Next ’23](https://cloud.withgoogle.com/next)  