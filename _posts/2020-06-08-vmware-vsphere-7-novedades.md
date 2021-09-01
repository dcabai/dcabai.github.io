---
layout: single
title:  "VMware vSphere 7 – Novedades"
categories: cloud vmware
tags: cloud vmware kubernetes seguridad update vmconaws multicloud
date:   2020-06-08 09:50:23 -0400
classes: wide
---

Ya pasó un poco más de un mes de la liberación de VMware vSphere 7.0, también pasamos por el  [VMware Empower Online](https://www.vmware.com/content/microsites/empower/home.html)  y siendo una de las actualizaciones más importantes de la marca, creo que es necesario repasar lo que nos trae. Ya les había contado en mi perfil de LinkedIn ([link](https://www.linkedin.com/posts/diegocabai_vmworld-tanzu-kubernetes-activity-6572219474513051651-H1OI)) durante el VMworld 2019 acerca de la integración de VMware vSphere con Kubernetes. Esto iba a ser posible gracias a  **Project Pacific**  que se encargaría de unir ambos mundos y que en las próximas versiones podríamos verlo realidad. Cumplieron con su palabra.

### Kubernetes

Primero lo primero, si eres nuevo en el mundo de contenedores y kubernetes, te dejo este link de cursos gratuitos de la  **KubeAcademy**  by VMware.  [https://kube.academy/](https://kube.academy/)

Lo importante es que Kubernetes ahora está integrado a vSphere a través de VMware Cloud Foundation 4, lo que permite a los desarrolladores continuar utilizando las interfaces estándar de la industria. Los administradores de vSphere también se benefician porque pueden ayudar a administrar la infraestructura de contenedores utilizando las mismas herramientas y habilidades que ya poseen. Para ayudar a unir estos dos mundos, introdujeron los vSphere  **Namespaces**, que permite a los administradores de vSphere crear un conjunto lógico de recursos, permisos y políticas que permiten un enfoque centrado en la aplicación.

### Distributed Resource Scheduler (DRS)

El famoso y conocido DRS tuvo una mejora significativa y además soporta el mundo de contenedores. DRS solía enfocarse en el estado del clúster y el algoritmo te recomendaba un vMotion cuando beneficiaba el equilibrio del clúster en su conjunto.

Pero ¿qué pasa con las máquinas virtuales individuales? ¿Cómo afectaría a sus vecinos? La nueva lógica DRS calcula una puntuación (**DRS Score**) en los hosts y mueve la VM a un host que proporciona la puntuación más alta. La mayor diferencia con respecto a la versión DRS anterior es que ya no equilibra la carga del host. Esto significa que DRS se preocupa menos por la utilización del host ESXi y prioriza el “bienestar” de VM.

![](https://www.cuatroi.com/wp-content/uploads/2020/06/image.png)

### Application Acceleration Enhancements

Hay muchas aplicaciones nuevas que utilizan  **inteligencia artificial (IA)**  y el  **machine learning (ML)**  que las empresas están usando. En vSphere 7, se ha incorporado  **Bitfusion**  directamente en el hipervisor. Éste, permite aprovechar la tecnología de virtualización de GPU para casos de uso de  **AI / ML**. Además está el nuevo Dynamic  **DirectPath I/O**, que es una nueva forma de configurar la exposición directa de los dispositivos PCIe a una máquina virtual.

### vSphere Lifecycle Manager

VMware presentó  **vSphere Lifecycle Management (VLCM)**, que reemplazará el viejo conocido vSphere Update Manager (VUM) utilizado para actualizaciones. Se ve un cambio de paradigma en la forma en que VMware maneja la gestión del ciclo de vida de los productos y realmente es un cambio esperado. No solo se podrá aplicar el estado deseado al hipervisor, sino también al firmware y los drivers del hardware físico. Creo que esto es fantástico, ya que cada vez que hay que actualizar un cluster, hay que revisar las matrices de versiones y es lo que más tiempo lleva. Ni hablar de los  **vSAN**  Ready Nodes donde esto se vuelve aún mas complejo, con esto podremos simplificar esa administración.

Además, dentro de vSphere Lifecycle Manager está el  **vCenter Server Update Planner**. Éste proporciona herramientas nativas para ayudar a planificar, descubrir y actualizar los entornos.

Es importante tener en cuenta que vCenter Server Update Planner solo funciona con vSphere 7 y versiones posteriores. Por lo tanto, Update Planner no puede ayudarte a planificar la actualización de vSphere 6.x a vSphere 7, pero simplificará drásticamente sus actualizaciones una vez que esté versión 7.

![](https://www.cuatroi.com/wp-content/uploads/2020/06/image-3.png)

![](https://www.cuatroi.com/wp-content/uploads/2020/06/image-2.png)

### vMotion

Al igual que con DRS, era necesario revisar el proceso de vMotion y analizar cómo mejorarlo para soportar las cargas de trabajo de hoy. Las máquinas virtuales con gran memoria y CPU, como los servidores de bases de datos  **SAP HANA y Oracle**, tuvieron algunos problemas para migrar en vivo usando vMotion. El impacto en el rendimiento durante el proceso de vMotion y el tiempo durante la fase de cambio significaron que los clientes no se sentían cómodos usando vMotion para estas grandes cargas de trabajo.

Con vSphere 7, se usa una vCPU dedicada para el rastreo de páginas, lo que significa que la VM y sus aplicaciones pueden seguir funcionando mientras se ejecutan los procesos de vMotion sin afectar la performance.

Otro proceso que se mejoró fue la copia de memoria. Antes de vSphere 7, la memoria se transfería entre los hosts en páginas de 4k. Ahora usa páginas de 1 GB, junto con algunas otras optimizaciones, para que esta transferencia de datos sea mucho más eficiente. Al hacer el cambio de host y copiar el mapa de bits, la mayoría de las páginas ya están en el host de destino de la transferencia original, por lo que se reduce el tiempo de transferencia de segundos a milisegundos.

### Intrinsic Security

Para implementar  **Multi-Factor Authentication (MFA)**  y no tener que agregarle todo lo disponible en el mercado al vCenter, se optó por la federación, que utiliza estándares abiertos de autenticación y autorización como OAUTH2 y OIDC. Con vSphere 7 e Identity Federation, vCenter Server puede comunicarse con un proveedor de identidad que tengan implementado y sacar la autenticación local. Un ejemplo sería integrarlo con los servicios de federación de Active Directory (ADFS). También está el **vSphere Trust Authority (vTA)**, que ayuda con los temas de certificados, KMS, UEFI y Trusted Platform Module (TPM). Literatura algo pesada para este breve resumen. En síntesis, si tenes un grupo de hosts que requieren alta seguridad, este punto es de interés para ti.

### Otros

Es importante mencionar, que ya no es posible implementar controladores de servicios de plataforma (PSC) externos o vCenter Server para Windows. Si tienes alguna de estas implementaciones, el instalador de vCenter Server 7 migrará automáticamente a un appliance vCenter Server con un PSC incorporado.

-   vCenter Appliance con múltiples tarjetas de red (NIC)
-   CLI actualizado
-   **VM Hardware 17**, donde incluye reloj de precisión (PTP)
-   **vCenter Server Profiles**, ahora te permite exportar la configuración por medio de API e importarlas en otro vCenter
-   **Versionamiento de VMs**  y Templates, ahora podes ver las versiones de una VM y sus templates en un formato tipo “Github” que resulta mas fácil tomar decisiones.
-   **vSAN File Services**, ahora podremos habilitar compartidos NFS en forma nativa
-   **Skyline Health**, el visor de “salud” que teníamos en vSAN ahora es para todos los componentes

### Conclusión

Definitivamente vSphere 7 es realmente una actualización sustancial y revolucionaria. Ha habido un gran enfoque en mejorar la vida de los clientes a través del nuevo ciclo de vida (VLCM) y las mejoras de seguridad. Y, con la incorporación de Kubernetes, está más que claro que vSphere es la tecnología para la nube híbrida.

El uso de Kubernetes es un estándar en los desarrolladores que crean aplicaciones y el hecho de poder tener esto, tanto OnPrem como en el Cloud y moverlos en forma natural entre éstas va a ser que sea la tecnología de nube híbrida elegida por la mayoría de los clientes.