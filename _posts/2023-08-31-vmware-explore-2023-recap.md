---
layout: single
title:  "VMware Explore 2023 US - Recap"
categories: vmware eventos cloud kubernetes
tags: cloud aws vmware azure kubernetes hybridcloud multicloud tanzu drp vmconaws nsx eventos vrealize sddc gcp aria devops 
date:   2023-08-31 12:50:23 -0400
classes: wide
---

![image-center](/assets/images/explore-2023/title.png){: .align-center}

Como ya es costumbre, paso a resumir algunos anuncios clave del último **VMware Explore 2023**, el antiguo VMworld. Ya pasaron algunos días, pero no quería dejar pasar esta oportunidad de entregarles un breve resumen de lo que para mi fue lo más relevante. En principio como hemos visto en este último tiempo en VMware, la compañía se estuvo centrando en la familia de soluciones Tanzu y Aria. Por eso la mayoría de los anuncios vienen desde esa perspectiva.

**Tanzu Mission Control**

Se anunció la capacidad de soportar lifecycle management (LCM) para Azure Kubernetes Service (AKS). Ya era soportado sobre el mismo servicio, pero en AWS, ahora se sumó la capacidad en Azure dando un guiño al soporte multi-cloud de la plataforma.

Link: [Reduce Multi-Cloud Silos with Added Azure Cluster Lifecycle Management Support via VMware Tanzu](https://tanzu.vmware.com/content/blog/remove-multi-cloud-silos-with-aks-cluster-lifecycle-management-support)  

**Tanzu Application Engine**

Se agregó la beta de Application Engine a Tanzu Application Platform, el cual está diseñado para introducir una capa de abstracción centrada en las aplicaciones para permitir que las mismas se ejecuten con un gobierno operativo y un cumplimiento consistente, dentro y entre las múltiples nubes. Esto viene a resolver muchos “dolores” de los desarrolladores, te dejo el enlace al blog del anuncio para que revises más detalles.

Link: [Designing VMware Tanzu Application Engine to Increase Collaboration, App Velocity, and Compliance](https://tanzu.vmware.com/content/blog/introducing-vmware-tanzu-application-engine)

**VMware Cloud Editions**

Los Cloud “Packs” ahora se conocen como Cloud Editions, te dejo estas imágenes para entender mejor que incluye cada edición.

![image-center](/assets/images/explore-2023/picture1.png){: .align-center}

![image-center](/assets/images/explore-2023/picture2.png){: .align-center} 

Link: [Compare VMware Cloud Software Editions](https://www.vmware.com/cloud-solutions/vmware-cloud.html#compare-editions)

**VMware NSX+**

Es un servicio basado en la nube que permite consumir y operar servicios de redes y seguridad de NSX, tanto para usar en nubes privadas como públicas. El servicio de NSX+ Policy Management como su nombre lo indica centraliza todo el manejo de políticas tanto en nubes privadas como públicas desde un solo lugar. El de NSX+ Intelligence entrega visibilidad y analítica en tiempo real de inspección de paquetes, tráficos, etc. Por último, NSX+ NDR entrega una solución escalable de detección y respuesta ante amenazas ideal para ser utilizada por el SoC.

![image-center](/assets/images/explore-2023/picture3.png){: .align-center} 

Link: [NSX+ Features](https://docs.vmware.com/en/VMware-NSX/4.1.1/nsx-feature-and-edition-guide/GUID-E25ACDFD-1687-4D50-9CA9-CD8AD5715E6C.html)

**vSphere 8 Update 2**

Hubo algunos anuncios del vSphere 8, donde no sólo está el update 2 sino también algunos beneficios que tendrán los que ya cuentan con vSphere+.

- ESXi Lifecycle Management Service
  Uno de los beneficios para los que cuenten con vSphere+ será un servicio de parchado de hosts desde la nube de VMware. Este servicio está más pensado para parchado de grandes cantidades de hosts ESXi. Si tu cluster es mediano o pequeño no notarás una mejora considerable en la función. Pero imagina que tienes 1000 clusters con 32000 hosts (como el ejemplo del sitio de VMware), el parchado se vuelve una tarea casi imposible. En esos casos, la eficiencia operacional lograda será considerable.

- Tiempo de inactividad reducido para actualizaciones de vCenter
  Bajará el tiempo requerido para los upgrades de vCenter, no hay mucho que decir de esta función, sólo que pasará de horas a minutos lo que permite actualizar más seguido dicho producto. ¿Cómo lo mejoraron? La copia de los datos se hará en línea y no con el vCenter offline. De esa forma redujeron el tiempo de downtime del vCenter.

- Soporte para Microsoft Entra ID (antes Azure AD) Identity Federation
  Agregaron el soporte a Azure AD que desde hace algunos días se llama Entra ID. Antes era soportado a través del ADFS (Federation Services), ahora lo soportará en forma nativa. Esto es ideal para unificar los privilegios elevados a la plataforma.

- VM Image Registry Service
  Básicamente es un repositorio de imágenes de VMs para ser consumidas por los DevOps y se pueden mantener y administrar directamente desde el llamado a una API.

También hay mejoras a nivel de uso de GPU, cantidad soportada y distribución de cargas en el DRS que utilizaban GPU.

<iframe width="560" height="315" src="https://www.youtube.com/embed/WEfbR7NPcI0?si=bZgDUWUIPYYb3WPH" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>  
<br/>
Link: [Announcing vSphere Q3 2023 Release](https://blogs.vmware.com/vsphere/2023/08/announcing-vsphere-q3-2023-release.html)

**vSAN 8 Update 2**

En el VMware Explore pasado se había anunciado el Express Storage Architecture (ESA) el cual fue un gran salto en la evolución de vSAN desde su primer lanzamiento. Si no recuerdas que era ESA, te dejo el link: [An Introduction to the vSAN Express Storage Architecture](https://core.vmware.com/blog/introduction-vsan-express-storage-architecture)

- VMware vSAN Max
  Es una nueva oferta de la familia vSAN, basada en ESA, con su nuevo modelo de implementación de almacenamiento desagregado, el cual permite escalar de manera elástica e independiente de del cómputo e implementar almacenamiento unificado de bloques, archivos y objetos basado en partners para maximizar la utilización y lograr un menor TCO.
  Link: [Introducing vSAN Max](https://core.vmware.com/blog/introducing-vsan-max)

**VMware Cloud on AWS Advanced**

Un nuevo modelo de suscripción que será desplegado en modelos de instancias i3en.metal y i4i.metal donde además incluirán todos los features especiales de seguridad y cloud management como NSX+, vSAN ESA, Aria, etc.

Link: [Announcing VMware Cloud on AWS: Advanced subscription tier](https://blogs.vmware.com/cloud/2023/08/22/announcing-vmware-cloud-on-aws-advanced-subscription-tier/)

**Edge Cloud Orchestrator**

El viejo y conocido SASE Orchestrator cambió de nombre a Edge Cloud Orchestrator y trae mas funciones para redes IT y OT. Las redes IT y OT están convergiendo cada vez mas en los clientes y era necesario agregarle capacidades de seguridad integral. 

**Anywhere Workspace**

El año pasado mostraron la visión de VMware acerca del “Autonomous Workspace” que si no la recuerdas te dejo abajo el enlace. Esa es la visión donde el concepto es que el escritorio haga todo “solo” y no dependa del equipo de TI. Me refiero a configurarse, remediarse e implementar la seguridad pertinente.

Dentro de esa visión fueron entregando capacidades y funciones a las plataformas de Workspaces, que también podrás verlas en el enlace que dejo justo debajo de esta sección.  En los anuncios de este año se encuentra la detección de una anomalía utilizando inteligencia artificial (AI) en el panel de Insights. Además, están los playbooks de remediación para corregir problemas comunes de forma automática. Y mucha más analítica, monitoreo y visualización de lo que pasa en las sesiones de escritorios y aplicaciones.

Link: [What’s new with digital employee experience: Announcements from VMware Explore 2023 Las Vegas](https://blogs.vmware.com/euc/2023/08/whats-new-with-digital-employee-experience-announcements-from-vmware-explore-2023-las-vegas.html)  
Link: [What’s new for Anywhere Workspace at VMware Explore 2023 Las Vegas](https://blogs.vmware.com/euc/2023/08/whats-new-for-anywhere-workspace-vmware-explore-2023-las-vegas-end-user-computing-announcements-horizon-workspaceone.html)  
Link: [Our journey to autonomous workspaces: VMware Explore 2022 update](https://blogs.vmware.com/euc/2022/11/our-journey-to-autonomous-workspaces-vmware-explore-2022-update.html)  

**VMware Cloud DR y VMware Ransomware Recovery**

Algunas mejoras en las capacidades de VMware Cloud DR  y Ransomware Recovery donde ahora podremos recuperar múltiples VMs en paralelo ante un ataque de Ransomware. Además, se mostró la tecnología de Cybersecure Storage que permitirá reducir el tiempo de recuperación de las máquinas a partir de los snapshots con deltas de información alojados en vSAN. Por último, la capacidad de recuperar las VMs directamente en la nube y se agrega Google Cloud VMware Engine como nube soportada para este servicio.

Link: [Innovations in Ransomware and Disaster Recovery](https://blogs.vmware.com/virtualblocks/2023/08/22/vmware-explore-2023-innovations-in-ransomware-and-disaster-recovery/)  
Link: [VMware Ransomware Recovery Now Protects Google Cloud VMware Engine Workloads](https://blogs.vmware.com/virtualblocks/2023/08/22/vmware-ransomware-recovery-now-protects-google-cloud-vmware-engine-workloads/)  

Algunas otras mejoras en **VMware Cloud Foundations** también donde agregaron componentes como los nombrados anteriormente de vSAN ESA, NSX+, AI, etc. y otras mejoras a los productos existentes.

Además del partnership con **NVIDA** para dar capacidades de AI sobre las capas de infraestructura. Esperemos que esta alianza nos traiga mejoras en las próximas actualizaciones de productos VMware. “VMware Private AI Foundation”

Cambios de nombres para el Q1 del 2024:

- El portafolio de VMware Tanzu incluye dos nuevas categorías de productos denominadas “Tanzu Application Platform” y “Tanzu Intelligence Services”.
- Tanzu Application Platform incluye los productos Tanzu Application Platform (TAP) y Tanzu for Kubernetes Operations (TKO), y el nuevo módulo Tanzu Application Engine.
- Tanzu Intelligence Services - Aria Cost powered by CloudHealth, Aria Guardrails, Aria Insights y Aria Migration pasarán a llamarse “Tanzu” y pasarán a formar parte de esta nueva categoría de Tanzu Intelligence Services.
  - Tanzu Hub y Tanzu Graph
  - Tanzu CloudHealth
  - Tanzu Guardrails
  - Tanzu Insights (actualmente conocido como Aria Insights)
  - Tanzu Transformer (actualmente conocido como Aria Migration)
- Aria Hub y Aria Graph ahora se llamarán Tanzu Hub
- Los VMware Cloud Packs ahora se llamarán VMware Cloud Editions.

Mirá todo lo nuevo en este link: [What’s New at VMware Explore 2023](https://www.vmware.com/vmware-explore-new.html)  

### Conclusión

Es uno de los eventos más importantes de tecnología, ya que la mayoría de los clientes poseen VMware en sus datacenters o en la nube. Por ello los anuncios y la visión de la compañía es seguida por muchas empresas, tanto clientes como socios tecnológicos. En este caso, es claro que el destino de la compañía está en las aplicaciones a través de Tanzu, las múltiples nubes y la seguridad de las cargas de trabajo estén donde estén. 
Como todo gigante de tecnología, está sumando la inteligencia artificial en varias de sus capas y con el partnership de NVIDIA creo que puede lograr grandes cosas hacia adelante. 