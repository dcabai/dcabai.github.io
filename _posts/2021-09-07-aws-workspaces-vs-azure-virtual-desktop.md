---
layout: single
title:  "AWS Workspaces vs Azure Virtual Desktop (AVD)"
categories: cloud aws azure
tags: cloud aws azure horizon vmware 
date:   2021-09-07 02:50:23 -0400
classes: wide
---
VDI fue y sigue siendo la figurita sexy de la pandemia al pasar todos a trabajo remoto y no depender de tecnología un poco más “legada” como una VPN. Digo legada porque una VPN en comparación con un VDI tiene menos características de **seguridad, acceso, escalabilidad, agilidad y flexibilidad.**

Si eres parte del equipo de TI de tu empresa y llegaron un día y te dijeron “tenes que habilitar VDI” seguramente te llegaron muchas dudas:

¿Cómo proporcionaremos el hardware y el software necesarios para que los empleados realicen su trabajo? ¿Lo hago en la nube? ¿Qué tecnología debo habilitar? ¿Uso tecnología del Cloud provider como AWS y Azure o debo ir por algo más robusto como VMware Horizon o Citrix?

El uso de un proveedor de nube para proporcionar infraestructura de escritorio virtual (VDI) a sus empleados es una excelente manera de resolver muchos de estos problemas sin tener que implementar una solución más robusta como VMware Horizon o Citrix, así que vamos a comparar rápidamente **Azure Virtual Desktop (AVS) **(anteriormente Windows Virtual Desktop) y **AWS Workspaces**.

Luego te comento algunas de las características robustas que pueden aportar **Horizon** o **Citrix** que no tienen AVD o Workspaces.

Pero primero un poco de qué es VDI:

### ¿Qué es una infraestructura de escritorios virtuales (VDI)?

El término **infraestructura de escritorios virtuales (VDI)** hace referencia al uso de máquinas virtuales para proporcionar y gestionar escritorios virtuales. El VDI aloja entornos de escritorio en un servidor centralizado y los distribuye a los usuarios finales según las necesidades.

Un VDI puede ser **persistente** o **no persistente**.

Con un VDI **persistente**, el usuario se conecta siempre al mismo escritorio y puede personalizarlo conforme a sus necesidades, se comporta igual que un computador personal físico.

En el VDI **no persistente**, los usuarios se conectan a escritorios genéricos y no se guardan los cambios, suele ser más sencilla y económica, puesto que no hace falta mantener escritorios personalizados entre sesiones.

### ¿Cuáles son las ventajas del VDI?

**Acceso remoto**: los usuarios pueden conectarse a sus escritorios virtuales desde cualquier ubicación o dispositivo, lo cual permite que los empleados puedan acceder fácilmente a todos sus archivos y aplicaciones para trabajar de forma remota desde cualquier lugar del mundo sin necesidad de establecer VPN previo.

**Ahorro de costos**: ya que el procesamiento tiene lugar en el servidor o entidad central, los requisitos de hardware para los dispositivos finales son mucho menores. Los usuarios pueden acceder a sus escritorios virtuales desde dispositivos antiguos, clientes ligeros e incluso tablets.

**Seguridad**: en un entorno de VDI, los datos se ubican en el servidor en lugar de guardarse en el dispositivo del cliente final. Esto sirve para proteger los datos en caso de que un dispositivo de punto de acceso sea robado o se vea comprometido.

**Gestión centralizada**: esto hace posible que se apliquen parches, actualicen o configuren todos los escritorios virtuales del sistema fácilmente.

### ¿Para qué se utiliza?

**Teletrabajo**: ya que resulta sencillo implementar y actualizar escritorios virtuales desde una ubicación centralizada, cada día más empresas implementan esta opción para los trabajadores remotos.

**Uso de dispositivos personales en el trabajo (BYOD)**: es la solución ideal para entornos que permitan o exijan que los empleados utilicen sus propios dispositivos debido a que ofrece mayor seguridad, ya que los datos se encuentran centralizados y no permanecen en el dispositivo del cliente final.

**Trabajo de tareas específicas o turnos**: con los escritorios no persistentes para callcenters es una solución ideal.

## AWS vs Azure - Características

Ambos productos ofrecen muchas de las mismas características, como conectividad remota desde cualquier lugar, uso de una aplicación nativa o navegador web, almacenamiento de archivos persistente, implementación de aplicaciones personalizadas, así que veamos en qué se diferencian.

Con **AWS Workspaces**, cada usuario obtiene su propio escritorio personal que puede ser el sistema operativo **Windows** o **Linux**. Hasta fines de Octubre de este año tiene una promoción con **50 usuarios en forma gratuita**:


![image-center](/assets/images/awsoffer.png){: .align-center}

En el lado de **Azure Virtual Desktop**, Windows será la única opción de sistema operativo y los usuarios pueden tener un escritorio personal o muchos usuarios pueden compartir una máquina virtual. Esta segunda opción es una buena manera de ayudar con los costos y reducir el recuento de máquinas virtuales.

Microsoft además tiene una oferta llamada **Windows 365** que fue anunciada este año donde puede entrar escritorios en modalidad SaaS como el Office 365. Tiene menos flexibilidad que la opción de AVS pero es mucho mas **simple** para las organizaciones que no tengan un equipo de TI.

El siguiente aspecto importante a considerar en AWS Workspaces, puedes usar tus **licencias** de Windows 10 actuales pero para eso debes tener un mínimo de 200 espacios de trabajo en la misma región.

## Precios

Ahora veamos el precio de cada oferta usando un mínimo de **100 estaciones**. Para el sizing tomaremos una máquina con **2 vCPU, 8 Gb de RAM** y con un sistema operativo **Windows**. No voy a agregar temas de directorio activo, vpn o tráfico, simplemente la oferta de VDI.

### Escenario de precios de AWS Workspaces 

Con esos requisitos en mente, y mirando la calcuadora de precios de AWS, vemos que una sola máquina virtual de 2 VCPU y 8 GB de RAM nos costará **USD 45/mes**; que también **incluye la licencia de Windows**. Entonces, para **100 usuarios**, nuestra factura sería de **USD 4.500/mes en total**.
**Calculadora**: https://calculator.aws/#

### Escenario de precios de Azure Virtual Desktop 

A continuación, Azure Virtual Desktop. Hay dos formas en que podemos ver los precios con Azure Virtual Desktop: donde cada usuario obtiene su propia máquina virtual (conocida como **Personal**), o donde muchos usuarios comparten una máquina virtual (conocida como **Pooled**).

#### Personal

Este escenario es similar a AWS porque son dedicados y vemos que una sola máquina virtual de 2 VCPU y 8 GB de RAM nos costará **USD 39/mes**; pero **no incluye la licencia de Windows.** Entonces, para 100 usuarios sin licencia, nuestra factura sería de USD 3900/mes en total y todavía tenemos que considerar las licencias! Supongamos que cada usuario usará la suscripción de Microsoft 365 Premium, que les permitirá usar máquinas virtuales de escritorio virtual de Azure y que cuesta **USD 20** por usuario al mes. Entonces, con todo eso en mente, sería un poco más de **USD 59/usuario/mes**. Para **100 usuarios**, eso equivale a **USD 5.900/mes en total.**

#### Pooled

Al volver a la calculadora de precios, esta vez seleccionamos Pooled que permite utilizar mejor los recursos y elegiré una máquina virtual según las mejores prácticas de Microsoft. Dado que son 100 usuarios y asumimos el tipo "Carga de trabajo **medio**", Microsoft recomienda un D8s_v4 (8 CPU virtuales y 32 GB de RAM). Ahora, si calculamos el precio de la máquina virtual, más un poco de los costos de almacenamiento obtenemos un total de **USD 500/mes para los 100 usuarios**, USD 5 por usuario no es gran costo a lo que debemos sumarle la suscripción para la licencia de Windows y nos quedaría unos **USD 25/mes por usuario y $ 2.500/mes para los 100**
**Calculadora**: https://azure.microsoft.com/en-us/pricing/calculator/

## Desempeño y confiabilidad

En cuanto al rendimiento y la confiabilidad, por mi experiencia en el uso de Azure Virtual Desktop y AWS Workspaces, diría que ambos funcionan de manera bastante **similar** con las aplicaciones nativas.

Por el lado de la confiabilidad, los espacios de trabajo de AWS ofrecen un SLA de tiempo de actividad del 99,9%. Azure Virtual Desktop, por otro lado, "se esfuerza por lograr al menos el 99,9% de disponibilidad" y "Microsoft no ofrece un acuerdo de nivel de servicio con respaldo financiero". Entonces, **si necesita un SLA garantizado, AWS Workspaces sería mejor opción**.

### ¿Cuál es el adecuado para mí: AWS Workspaces o Azure Virtual Desktop?

Después de analizar las funciones, los precios, el rendimiento y la confiabilidad de ambas ofertas, ¿cuál debería elegir? Bueno, eso dependerá de cada situación (y de la cantidad de personal de su empresa). Hay temas de conectividad, otros servicios dentro de la nube, latencia de las regiones que también pueden entrar en la decisión.

### ¿Qué gran diferencia tiene VMware Horizon o Citrix sobre estas ofertas?

Amazon WorkSpaces y Azure Virtual Desktop carecen de muchas funciones de **clase empresarial** y solo ofrecen escritorios persistentes o compartidos, pero no se “meten” mucho en las aplicaciones para éstos.

**Horizon Cloud** se adapta a cualquier dispositivo y red para poder entregar la mejor posible experiencia del usuario final. Incluso hay una oferta de Horizon Cloud sobre Azure que aprovecha parte del AVD. Algunas de las características que tiene Horizon por sobre estos VDI nativos:

• **Unity Touch** – Para que la experiencia desde el móvil sea mas amena hacia el usuario final.
• **USB y multimedia** – Mayor soporte y cantidad de dispositivos que se pueden usar
• **vGPU siempre disponible** – Para los que requieren procesamiento gráfico
• **Inicio de sesión único para aplicaciones y escritorios** – SSO entre Aplicaciones y Escritorios sin necesidad de terceros
• **True app publishing** – Horizon Cloud ofrece una verdadera entrega de aplicaciones y escritorios como servicio en la nube a cualquier dispositivo. No es el escritorio por un lado y las aplicaciones por el otro.