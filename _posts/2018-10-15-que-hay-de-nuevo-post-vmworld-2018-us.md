---
layout: single
title:  "Qué hay de nuevo? post-VMworld 2018 US"
categories: cloud vmware eventos
tags: vmware cloud vmconaws hybridcloud nsx
date:   2018-10-15 12:50:23 -0400
classes: wide
---

Ya pasó un tiempo desde el VMworld US 2018, es mas, estamos cerca del de Barcelona, sin embargo, no quería dejar pasar la oportunidad de contar algunas novedades anunciadas en dicho evento.

-   **vSphere Platinum:** es una nueva oferta de licenciamiento que incluye el Enterprise Plus +  **[AppDefense](https://www.vmware.com/products/appdefense.html)**. AppDefense es un producto de seguridad para endpoint que protege aplicaciones corriendo en ambientes virtualizados. Al venir ambos juntos, esta edición incluye un plugin para vCenter que hace la integración mucho mas natural. Basicamente lo que hace AppDefense es aprender el correcto funcionamiento de una aplicación y cuando detecta que esto cambia puede deberse a algun problema de seguridad, ya sea malware, un intruso, etc. Algunas de las funciones incluyen  **Secure Boot**,  **Virtual TPM**, etc

[](https://www.cuatroi.com/wp-content/uploads/2018/10/AppDefense-Console-1030x515.png)

Consola VMware AppDefense

![](https://www.cuatroi.com/wp-content/uploads/2018/10/AppDefense-Console-300x150.png "AppDefense Console")

[](https://www.cuatroi.com/wp-content/uploads/2018/10/AppDefense-vCenter-1030x549.png)

Integración con VMware vCenter

![](https://www.cuatroi.com/wp-content/uploads/2018/10/AppDefense-vCenter-300x160.png "AppDefense vCenter")

-   **vSphere 6.7 Update 1:** Ahora si viene el cliente con todas las funciones  **HTML5**  sin necesidad de estar cambiando entre el HTML5 y el Web Client anterior. Soporte para  **NVIDIA vGPU**  VMs, la vCenter Server  **Convergence Tool**  que sirve para migración de PSC, mejoras para **HCI**  y  **vSAN**  y mejoras a la  **Content Library**. Mas info en este  [link](https://blogs.vmware.com/vsphere/2018/08/under-the-hood-vsphere-6-7-update-1.html).

![](https://www.cuatroi.com/wp-content/uploads/2018/10/vSphere67U1_features_blog-1.png "vSphere67U1_features_blog-1")

-   **ESXi en dispositivos ARM 64bit**: Un guiño al IoT donde podrán correr ESXi en dispositivos ARM del tipo Raspberry Pi.
-   **vRealize Operations (vROps) 7.0:** Uno de mis productos favoritos por el valor que le entrega al cliente de su plataforma. En esta versión mejoraron las operaciones autónomas (**self-driven operations**) agregándole mas capacidades y funciones. Mejoraron la integración con el vRealize Automation. Cambiaron un poco la  **interfaz**  del usuario haciéndola un poco mas simple. Además de mover las VMs por capacidad de los nodos o el cluster, ahora podrá aprender necesidades del  **negocio**  y en base a aquello mover los workloads donde corresponda. Un caso de uso es licenciamiento por ejemplo. El  **What-If**  **Analysis**  ahora puede ayudarte a llevar los workloads a AWS por ejemplo. Importante por temas de cumplimiento, trae embebido el **vSphere config & compliance**​: PCI, HIPAA, DISA, FISMA, ISO, CIS. Además de agregarle la integración con  **Wavefront**.
-   **vRealize Automation 7.5:** Modernizaron la interfaz de usuario (**UI**) del Automation y Orchestrator (vRO). Integración con  **ServiceNow**  y con **NSX-T**  OnPremise.  **Ansible Tower**  será un endpoint nativo dentro de vRA 7.5. Integración de **Kubernetes Cluster Management cpn VMware Pivotal Container Services (PKS).**  Mejoras para  **AWS**,  **Azure**  y  **Google**  **Cloud**  apostando por el multi-cloud.
-   **VMware vCloud Director 9.5:** Este producto tuvo un major upgrade donde agregaron integración con  **NSX**, nueva  **UI**  en  **HTML5**,  **RBAC**, etc. mas info en este  [link](https://blogs.vmware.com/vcloud/2018/08/vmware-vcloud-director-9-5.html?src=vmw_so_vex_mande_12).
-   **Amazon Relational Database Service (RDS) on VMware:** La apuesta de VMware on AWS para integrar ambos mundos en la era del multi-cloud. Se puede trabajar OnPremise y luego llevar la BBDD a la nube o trabajar en forma híbrida. Se hace mas natural su migración entre ambas plataformas. Esta fue una mejora del  **VMwareOnAWS**.
-   **VMware Cloud Foundation (VCF) 3.0:** Nueva versión de esta arquitectura que integra todos los componentes de infraestructura y software necesarios para un SDDC que se puede conectar tanto OnPremise como hacia VMwareOnAWS haciendo la nube híbrida mucho mas simple. En esta versión mejoraron la UI, agregaron la posibilidad de llevar tu propia red ethernet, y agregaron soporte a mas fabricantes de HW

![](https://www.cuatroi.com/wp-content/uploads/2018/10/VMware-Cloud-Foundation.png "VMware Cloud Foundation")

-   **Public Cloud:** Varios anuncios de prodcutos y tecnologías para integrar el Cloud público. VMware Cloud Assembly, VMware Service Broker, VMware Code Stream, Wavefront by VMware, Log Intelligence, etc. Mas información en este  [link](https://cloud.vmware.com/).
-   **Cloud Health:** Una plataforma para poder administrar las multi-cloud, tanto en costo, seguridad, operación, etc. Lean mas sobre esta herramienta en este  [link](https://www.cloudhealthtech.com/).
-   **NSX Cloud:** Ahora si que podemos montar NSX en cualquier parte. Con esto podemos entregar micro-segmentación a aplicaciones nativas cloud con políticas dinámicas y administrar todo desde mis operaciones de data center. De esta forma no perdemos control sobre lo que está pasando en estos clouds públicos.

En síntesis, VMware sigue por el camino que viene demostrando hace un tiempo, el multi-cloud, incorporando nuevas funciones, capacidades y productos para poder atender todas las necesidades de los clientes en ese ámbito.
