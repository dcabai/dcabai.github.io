---
layout: single
title:  "Creando un VMX para Usar con VMware"
categories: vmware
tags: vmware legacy
date:   2009-05-19 05:50:23 -0400
classes: wide
---
Muchos dirán, para qué necesito crear un **VMX** si el mismo VMware ESX lo hace por mi a través del asistente o bien el VMware Workstation. Pero qué pasa si estamos en nuestras notebooks haciendo pruebas y no tenemos licencia de ninguno de los dos. El producto gratuito que podemos usar y es muy robusto es el VMware Player, pero lamentablemente sólo sirve para ejecutar una máquina virtual y no para crearla. En ese caso debemos recurrir a la creación de un archivo VMX que contiene la máquina virtual en si y el archivo o los archivos de los discos duros. Si ya tenemos un disco duro creado con anterioridad para otra máquina virtual o convertimos algún vhd en un vmdk podemos usarlo especificándolo dentro del vmx.  
  
Si bien el VMX es un archivo de texto y podemos editarlo con un simple Notepad o el que mas te guste, no todos conocen la estructura del mismo y lo que se puede o no completar para que funcione correctamente la VM.  
  
Si editamos el archivo de la máquina virtual del FreeNAS antes comentado en este sitio vamos a ver algo por el estilo:
```batch
 1: .encoding = "windows-1252"
 2: config.version = "8"
 3: virtualHW.version = "4"
 4: scsi0.present = "TRUE"
 5: scsi0.virtualDev = "lsilogic"
 6: memsize = "256"
 7: ide0:0.present = "TRUE"
 8: ide0:0.fileName = "FreeNAS0.69_disk1.vmdk"
 9: ide1:0.present = "TRUE"
 10: ide1:0.autodetect = "TRUE"
 11: ide1:0.deviceType = "cdrom-raw"
 12: floppy0.startConnected = "FALSE"
 13: floppy0.autodetect = "TRUE"
 14: ethernet0.present = "TRUE"
 15: ethernet0.wakeOnPcktRcv = "FALSE"
 16: usb.present = "FALSE"
 17: sound.present = "FALSE"
 18: sound.fileName = "-1"
 19: sound.autodetect = "TRUE"
 20: roamingVM.exitBehavior = "go"
 21: displayName = "FreeNAS0.69"
 22: guestOS = "freebsd"
 23: nvram = "FreeNAS0.69.nvram"
 24: virtualHW.productCompatibility = "hosted"
 25: ft.secondary0.enabled = "TRUE"
 26: tools.upgrade.policy = "useGlobal"
 27:  
 28: extendedConfigFile = "FreeNAS0.69.vmxf"
 29:  
 30: floppy0.fileName = "A:"
 31:  
 32: scsi0:0.present = "TRUE"
 33: scsi0:0.fileName = "FreeNAS0.69_disk2.vmdk"
 34: scsi0:1.present = "TRUE"
 35: scsi0:1.fileName = "FreeNAS0.69_disk3.vmdk"
 36: scsi0:2.present = "TRUE"
 37: scsi0:2.fileName = "FreeNAS0.69_disk4.vmdk"
 38: scsi0:3.present = "TRUE"
 39: scsi0:3.fileName = "FreeNAS0.69_disk5.vmdk"
 40: scsi0:4.present = "TRUE"
 41: scsi0:4.fileName = "FreeNAS0.69_disk6.vmdk"
 42: scsi0:5.present = "TRUE"
 43: scsi0:5.fileName = "FreeNAS0.69_disk7.vmdk"
 44: scsi0:6.present = "TRUE"
 45: scsi0:6.fileName = "FreeNAS0.69_disk9.vmdk"
 46: scsi0:8.present = "TRUE"
 47: scsi0:8.fileName = "FreeNAS0.69_disk8.vmdk"
 48: scsi0:9.present = "TRUE"
 49: scsi0:9.fileName = "FreeNAS0.69_disk10.vmdk"
 50: scsi0:10.present = "TRUE"
 51: scsi0:10.fileName = "FreeNAS0.69_disk11.vmdk"
 52: floppy0.present = "FALSE"
 53:  
 54: ide1:0.fileName = "auto detect"
 55:  
 56: ethernet0.addressType = "generated"
 57: uuid.location = "56 4d f2 55 43 ee 3d 1f-7e 0e 09 2d e4 5f eb e3"
 58: uuid.bios = "56 4d f2 55 43 ee 3d 1f-7e 0e 09 2d e4 5f eb e3"
 59: ide0:0.redo = ""
 60: scsi0:0.redo = ""
 61: scsi0:1.redo = ""
 62: scsi0:2.redo = ""
 63: scsi0:3.redo = ""
 64: scsi0:4.redo = ""
 65: scsi0:5.redo = ""
 66: scsi0:6.redo = ""
 67: scsi0:8.redo = ""
 68: scsi0:9.redo = ""
 69: scsi0:10.redo = ""
 70: vmotion.checkpointFBSize = "17498112"
 71: ethernet0.generatedAddress = "00:0c:29:5f:eb:e3"
 72: ethernet0.generatedAddressOffset = "0"
 73:  
 74: ide1:0.startConnected = "FALSE"
 75:  
 76: tools.remindInstall = "FALSE"
```
Si nosotros sabemos qué significan las líneas y qué debemos completar entonces podemos abrir el editor de texto que mas les guste y crear los archivos sin problemas. Ahora, si para ustedes es un idioma nuevo podemos usar algunas herramientas para generar dichos archivos VMX que luego utilizaremos con el VMware Player.

Por ejemplo, si vemos uno de los parámetros dice **[guestOS = "freebsd"]** y si usamos la lógica esto prepara la VM para correr un sistema operativo **FreeBSD**, pero qué podríamos introducir en este campo para correr un Windows por ejemplo? Bueno, acá les dejo un link con todas las opciones de sistemas operativos para poner en un VMX por si lo quieren hacer a mano. 
Link - [Guest-OS vmx file Specifications](http://sanbarrow.com/vmx/vmx-guestos.html)

  
![image-left](assets/images/CreandounVMXparaUsarconVMware_C203/image.png "EasyVMX"){: .align-left} Luego tenemos una opción web **EasyVMX** donde nos crea directamente el vmx a partir de un formulario. Esto es muy sencillo, respondemos las preguntas del formulario, le hacemos click sobre el botón final “Create Virtual Machine” y podremos descargar el vmx con las especifacaciones que nosotros mismos hicimos. Ya llevan mas de un millón de VMs creadas a través de este servicio y es muy seguro, fácil y práctico ya que no requiere que instales ni corras nada, respondé un formulario y listo.

![image-left](assets/images/CreandounVMXparaUsarconVMware_C203/image_3.png "VMBuilder"){: .align-left} Otra opción para trabajar online en la creación del VMX es **VMBuilder**. Es una aplicación mucho mas desarrollada, y optimizada para Firefox donde también debemos completar los campos del formulario pero mas parecido a una aplicación que a una página web. Una vez completadas las preguntas podremos exportar el archivo vmx con la configuración y correrlo en nuestro VMware Player sin problemas. También lo he probado y es muy bueno al igual que el anterior. Lo bueno de este es que podemos importar un vmx y editarlo.

![image-left](assets/images/CreandounVMXparaUsarconVMware_C203/image_4.png "VMX-Builder"){: .align-left} Por último si somos amantes de los scripts y no de las páginas web online o simplemente porque no tenemos internet donde debemos correrlo tenemos la opción de bajar un CMD que nos hace las mismas preguntas que las páginas anteriores y nos crea un VMX con las respuestas. No es algo complicado de armar ya que el contenido del archivo una vez aprendido es muy simple. El **VMX-Builder** también funciona muy bien y es recomendable si no tenes conexión a internet y si sos mas amante de los scripts. También sirve para modificarlo a gusto ya que las webs no lo podemos hacer.

Bueno, ya te presenté las diferentes formas de crear un VMX para que lo ejecutes con tle VMware Player, ahora solo resta que empieces a hacer pruebas con dichas aplicaciones y empieces a crear tus máquinas virtuales totalmente portátiles y sin ninguna herramienta compleja por detrás.

Link - [Guest-OS vmx file Specifications](http://sanbarrow.com/vmx/vmx-guestos.html)  
Link - [EasyVMX.com](http://www.easyvmx.com/)  
Link - [VMBuilder](http://dcgrendel.thewaffleiron.net/vmbuilder/)  
Link - [VMX-Builder Script](http://sanbarrow.com/vmxbuilder.html)