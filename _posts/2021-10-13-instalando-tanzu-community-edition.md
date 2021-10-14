---
layout: single
title:  "Instalando Tanzu Community Edition (TCE)"
categories: vmware 
tags: cloud aws vmware azure kubernetes hybridcloud multicloud
date:   2021-10-13 02:50:23 -0400
classes: wide
---
![image-left](/assets/images/tce/tanzu-community-edition-logo.png){: .align-left} Una de las grandes novedades de VMware fue la liberación de VMware Tanzu Community Edition (TCE), el cual es gratuito y acerca **Tanzu Kubernetes** a cualquiera ya que permite que puedas instalarlo en tu máquina o en alguna nube.

## ¿Qué es TCE y por qué debería importarte?

Actualmente puede ser un desafío para los usuarios finales (administradores, arquitectos, desarrolladores, operadores de plataforma, etc.) **lograr  experiencia**  con Tanzu de VMware. Algunos de los desafíos pueden incluir  descargar el software, obtener la licencia y tener los recursos necesarios para ejecutarlo. TCE tiene como objetivo  suministrar una experiencia  simple para cualquier persona que quiera hacerse con una plataforma Kubernetes de nivel empresarial, que está completamente equipada con las características de Tanzu. TCE es fácil de usar, está disponible  **gratuitamente** para que cualquiera pueda descargarlo y usarlo con fines de aprendizaje, prueba, desarrollo y preproducción.

Además, TCE también incluye características más nuevas que no se encuentran en la oferta comercial de Tanzu (todavía) y características experimentales que la comunidad será la primera en probar. 
TCE también incluye paquetes adicionales que se pueden instalar opcionalmente y que pueden ayudar con la construcción, administración, implementación y ejecución de aplicaciones y servicios modernos. Entre ellos **Grafana, Prometheus, Harbor, Knative (Serverless), Velero**, etc.

## Instalación, Simple?

En cierta forma, si, pero los prerrequisitos son bastantes si lo estas ejecutando en Windows por ejemplo. Es importante que sigas la documentación oficial, el link abajo de todo, y puedas completar todos los pasos. Tienes que instalar **Docker**, **Kubectl**, **Tanzu** y si lo vas a ejecutar en la nube como Azure o AWS, debes instalar su **CLI** también. Algunos de estos links están abajo, aunque en la documentación de TCE también están.
**La nube no es obligación**, viene con soporte para una implementación local de Docker por lo que cualquier persona, con capacidad en su notebook, puede ejecutar Tanzu Kubernetes sin requerir un datacenter o gastar dinero en la nube.

Cuando descargas TCE verás que es un Batch con varios EXE. El Batch copia estos archivos en diferentes ubicaciones.

![image-center](/assets/images/tce/tanzu1.png){: .align-center} 

![image-center](/assets/images/tce/tanzu2.png){: .align-center} 

![image-center](/assets/images/tce/tanzu3.png){: .align-center} 

Luego puedes verificar si Tanzu quedó correctamente instalado y está en el PATH con
```batch
tanzu version
```
![image-center](/assets/images/tce/tanzu4.png){: .align-center} 

Ahora si podemos crear el Cluster, donde para esta primera prueba solo crearé un **Standalone Cluster** en vez de un Management Cluster + Workload Cluster.

```batch
tanzu standalone-cluster create --ui
```
Yo le agregué al final de esa sentencia esto adicional para hacer el bind y usar Chrome, pero no es obligatorio:

```batch
tanzu standalone-cluster create --ui --bind 127.0.0.1:8080 --browser chrome
```

Si estas usando Windows, como yo, y recibes este **error**:

> Downloading TKG compatibility file from 'projects.registry.vmware.com/tkg/framework-zshippable/tkg-compatibility'
> Error: unable to create Tanzu Standalone Cluster client   Cause: unable to ensure prerequisites: unable to ensure tkg BOM file: failed to download TKG compatibility file from the registry: failed to list TKG compatibility image tags: Get "https://projects.registry.vmware.com/v2/": x509: certificate signed by unknown authority

Edita el archivo de configuración que se encuentra en **%USERPROFILE%\.Config\tanzu\tkg\config.yaml** y reemplazalo con el siguiente contenido:

```yaml
release:
    version: ""
TKG_CUSTOM_IMAGE_REPOSITORY_SKIP_TLS_VERIFY: true
```

Ahora es un simple asistente donde nos pide alguna información de redes, nombres y ID's para el caso de Azure como lo hice yo y la instalación se realiza sin problemas.

![image-center](/assets/images/tce/tanzu5.png){: .align-center} 

![image-center](/assets/images/tce/tanzu6.png){: .align-center} 

![image-center](/assets/images/tce/tanzu7.png){: .align-center} 

**En Azure** vemos como se van creando los recursos mientras avanza la instalación.

![image-center](/assets/images/tce/tanzu8.png){: .align-center} 

**En AWS** si elegimos usar CloudFormation también podemos ir viendo como se va creando el Stack completo en el proceso.

![image-center](/assets/images/tce/tanzu10.png){: .align-center} 

Después de unos minutos, la implementación se completa y ahora está listo para ser accedido.

![image-center](/assets/images/tce/tanzu9.png){: .align-center} 

![image-center](/assets/images/tce/tanzu11.png){: .align-center} 

TCE se está desarrollando **abiertamente** con la comunidad y puedes participar visitando los repositorios de Github y links de documentación a continuación:

Link: [Documentación Tanzu Community Edition](https://tanzucommunityedition.io/docs/latest/installation-planning/)  
Link: [Github Tanzu Framework](https://github.com/vmware-tanzu/tanzu-framework)  
Link: [Github Tanzu Community Edition](https://github.com/vmware-tanzu/community-edition)  
Link: [Descargar Tanzu Community Edition](https://tanzucommunityedition.io/download/)  
Link: [Docker Desktop for Windows](https://docs.docker.com/desktop/windows/install/)  
Link: [Kubectl for Windows](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/)  
Link: [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli)  
Link: [Anuncio de TCE](https://tanzu.vmware.com/content/blog/vmware-tanzu-community-edition-announcement)