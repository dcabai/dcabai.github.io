---
layout: single
title:  "Instalando Kasten en Tanzu Community Edition (TCE)"
categories: vmware veeam kubernetes
tags: cloud aws vmware azure kubernetes hybridcloud multicloud veeam tanzu backup drp
date:   2021-10-14 02:50:23 -0400
classes: wide
---
Ahora que tengo mi Tanzu Community Edition (TCE) puedo jugar con otras herramientas para Kubernetes. En este caso instalé **Kasten by Veeam** para respaldos de contenedores. No es que necesite respaldos en mi ambiente de ultra laboratorio, sino que sirve para ver lo simple del proceso del despliegue y habilitación de dichos respaldos.

Para instalarlo necesitamos tener **Helm** el Package Manager instalado.  [Link](https://helm.sh/)

Agregamos el repositorio de las gráficas de Kasten con Helm.
```batch
helm repo add kasten https://charts.kasten.io/
```
Creamos el namespace donde vamos a instalar Kasten, dejé el por defecto.
```batch
kubectl create namespace kasten-io
```
Y luego ejecutamos su instalación.
```batch
helm install k10 kasten/k10 --namespace=kasten-io
```

![image-center](/assets/images/kasten/Kasten1.png){: .align-center} 

Podemos ir monitoreando los pods hasta que todos estén en estado Running.
```batch
kubectl get pods --namespace kasten-io --watch
```

![image-center](/assets/images/kasten/Kasten2.png){: .align-center} 

Y por último redireccionamos el acceso por navegador.
```batch
kubectl --namespace kasten-io port-forward service/gateway 8080:8000
```

![image-center](/assets/images/kasten/Kasten3.png){: .align-center} 

Detecta las aplicaciones que tengo corriendo en el cluster automáticamente, donde vemos el namespace **tanzu-rocks** que creamos en el post anterior donde instalamos TCE.

![image-center](/assets/images/kasten/Kasten4.png){: .align-center} 

Y luego ya podemos crear políticas de respaldo la cual voy a asignarsela a tanzu-rocks.

![image-center](/assets/images/kasten/Kasten5.png){: .align-center} 

Como se ve, bien simple, liviano y simple de usar como toda la familia de productos de Veeam. Si quieren darle una mirada a la solución, como ven es facil de instalar y pueden hacerlo no solo sobre TCE sino también sobre un cluster de AWS, Azure o GCP si es que tienen créditos en dichas nubes. Quedan algunas cositas por resolver porque sobre TCE no es todo tan natural al parecer pero ya lo iré resolviendo.

Link: [Documentación de Kasten](https://docs.kasten.io/latest/)  
Link: [Kasten Homepage](https://www.kasten.io/)  
Link: [Descargar Kasten](https://www.kasten.io/try-kasten-k10?__hstc=78384331.b2c5a47db1002918011e6dfbe7dee47c.1634180149206.1634180149206.1634180149206.1&__hssc=78384331.90.1634180149206&__hsfp=1597795017&hsutk=b2c5a47db1002918011e6dfbe7dee47c&contentType=standard-page)  
Link: [Sitio de Entrenamiento de Kasten y Kubernetes](https://learning.kasten.io/)  