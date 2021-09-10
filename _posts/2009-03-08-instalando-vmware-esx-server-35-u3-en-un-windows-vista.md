---
layout: single
title:  "Instalando VMware ESX Server 3.5 U3 en un Windows Vista"
categories: vmware 
tags: vmware legacy
date:   2009-03-08 05:50:23 -0400
classes: wide
---
Cabe aclarar de entrada que la razón por la cual uno querría hacer esto es para estudiar o bien para testing de alguna aplicación. La idea es poder correr un VMware ESX Server dentro de un sistema operativo ya instalado en el equipo. A simple vista no parece posible ya que el ESX Server es un sistema operativo de base, es un hypervisor, virtualización “bare metal” y no como VMware Server por ejemplo que si se instala en un Windows.  
  
A mi me surgió la necesidad de poder hacerlo ya que estaba estudiando para el examen de VMware y lograr la certificación VCP. En este caso necesitaba hacer pruebas con servidores ESX incluso mas de uno y no disponía del hardware y encontré la solución de la mano de [xtravirt](http://www.xtravirt.com).  
  
Ellos lograron poder instalar un **VMware ESX Server 3.5** en un **VMware Workstation 6** o bien si queres la opción gratuita en un VMware Player. Es tan simple como ingresar a su sitio web [Xtravirt Knowledge](http://knowledge.xtravirt.com/) y ahí bajar la solución deseada. En mi caso donde utilicé el VMware Player sobre Windows Vista bajé esa opción desde su web. Descargás un ZIP con un setup.exe y un PDF. En el archivo PDF encontrás los paso a paso para poder lograr esto y el Setup te instala las máquinas virtuales necesarias para poder lograr esta instalación.  
  
En las imágenes siguientes ven como inicia la instalación de VMware ESX Server 3.5 U3 sobre mi Windows Vista SP1. Mi laptop es un Intel Core 2 Duo con 2Gb de RAM y así y todo logra funcionar igual.  
  
![image-center](/assets/images/ab783b520287_451/image.png "image"){: .align-center} ![image-center](/assets/images/ab783b520287_451/image_3.png "image"){: .align-center}  
  
**Requerimientos**:  
[VMware Player](http://www.vmware.com/download/player/): Es gratuito y soporta la ejecución de máquinas virtuales creadas con VMware. Lo bueno es que podemos utilizar otros Appliance que tengan imágen VMware con este mismo producto.  
  
[VMware ESX 3.5 U3 ISO](https://www.vmware.com/tryvmware/?p=vi3&lp=1): Requiere la imagen del producto para poder instalarlo. Es la versión Trial pero para nuestros propósitos nos alcanza y sobra ya que esto de ninguna manera será producción.  
  
**Hardware**: Extensiones de Virtualización Intel VT o AMD-V habilitadas en el BIOS.  
  
Luego basta con iniciar la aplicación que instalamos de xtravirt que ejecuta el VMware Player con la imágen creada e inicia la instalación del ESX Server en nuestro Vista. Es totalmente operativo, podemos crear VMs, y hacer todo tipo de tareas. Lo mejor de todo es que hasta podemos hacer un cluster HA ya que podemos crear mas de un ESX Server tan sólo con copiar un directorio. En el PDF te lo explica, pero es muy sencillo y obviamente que el Virtual Center se puede instalar junto con un SQL en una VM.  
  
En los artículos siguientes les comento como simular un hardware de Storage NFS e iSCSI así logran probar todo el paquete completo.