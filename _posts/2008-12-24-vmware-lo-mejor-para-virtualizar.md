---
layout: single
title:  "VMware, lo Mejor para Virtualizar?"
categories: vmware 
tags: vmware legacy
date:   2008-12-24 05:50:23 -0400
classes: wide
---
Seguimos hablando sobre virtualización y en particular sobre VMware. Tengo para compartir algunos sitios, textos y discusiones interesantes sobre VMware, herramientas de terceros y scripts que podemos utilizar para mejorar nuestra administración diaria. Si te interesa la virtualización entonces tenes que leer lo que sigue en este artículo porque vas a poder potenciar y ganar mucho tiempo al día.  
  
Voy a comenzar comentando un artículo en PDF por parte de VMware donde compara sus features y costos con Microsoft Hyper-V y Citrix XenServer sus competidores mas actualizados y activos a la fecha. No sólo los compara a nivel de funciones sino que a nivel costos de licencias cuando uno debe virtualizar 10, 100 o 1000 equipos lo que veo interesante para grandes compañías con ideas a futuro.  
  
Por ejemplo, al comprar VMware con Hyper-V virtualizando 1000 VM’s y con soporte oficial por 2 años, Microsoft es un poco mas económico, pero hay ciertas funcionalidades que no posee lo que puede llegar a ser interesante gastar ese dinero extra pero ganarlo en funciones del producto.  
  
Si tenes que analizar y planificar tu sistema de virtualización para la compañía te recomiendo que leas el siguiente PDF. Igualmente hay que analizarlo en detalle porque el PDF dice que SCVMM no ofrece balanceo de carga dinámico, etc. etc. que si lo ofrece a través del PRO, por ende hay que analizar toda la información, nunca escuches un solo lado.   
  
Ya que estamos hablando de SCVMM hay mitos dando vueltas, versiones de qué hace uno y qué hace el Virtual Center, etc. Hay una muy buena discusión en el foro de VMware donde detallan que hace cada uno, qué puede hacer y que no. Te recomiendo que también lo leas porque es muy instructivo e interesante.  
  
Link:  [Virtual Center vs. MS SystemCenter Virtual Machine Manager (SCVMM)](http://communities.vmware.com/message/1091646)  
  
También debo recomendarte que te bajes la demo gratuita Trilead VM Explorer. Esta es una herramienta llena de cosas útiles para los administradores de VMware.  
  
Entre los features que tiene podemos administrar varios servidores a la vez desde la misma interfaz gráfica, ya sea ESX, Linux y FreeBSD. Se puede hacer copia de archivos entre servidores con un simple drag&drop y creo que es uno de los mejores features que tiene. Se puede hacer simple backup y restore de los equipos desde el ESX a cualquier plataforma. Soporta ESX 3i y programar tareas. Creo que es una herramienta a analizar a la hora de virtualizar.  
  
Link:  [VMX - Trilead VM Explorer](http://www.trilead.com/Products/VM_Explorer/)  
  
Llegó la hora de los scripts… en artículos pasados comenté sobre usar PowerShell para administrar VMware. Para poder administrar estos scripts o bien sacarles el jugo podemos usar el PowerGUI.  
  
PowerGUI es una herramienta gráfica desde donde podemos crear los scripts, ejecutarlos, etc. En este caso a dicha herramienta se le pueden agregar “Power Packs” con diferentes tecnologías para poder administrar las VMware en este caso o un SQL por ejemplo. En este caso comentamos los power packs de virtualización. Existen PowerPacks para VMware, Hyper-V y XenServer, así que te recomiendo que los revises. Este pack por ejemplo nos va a permitir hacer reportes, administrar varios hosts con un único logon de credenciales, administrar y soportar la plataforma de manera rápida y ágil.  
  
Link:  [PowerGUI Home](http://www.powergui.org/index.jspa)  
Link:  [VMware Infrastructure Management PowerPack](http://www.powergui.org/entry.jspa?categoryID=290&externalID=1802)  
Link:  [All Virtualization PowerPacks](http://www.powergui.org/kbcategory.jspa?categoryID=290)  
  
Qué le podemos agregar el ítem anterior, simple los scripts de PowerShell que todo administrador debe tener en su poder para poder llevar adelante dicha administración.  
  
Link:  [Quick Migration](http://mikedatl.typepad.com/mikedvirtualization/2008/10/quick-migration.html)  
Link:  [Reporting into Microsoft Word](http://communities.vmware.com/docs/DOC-7070)  
Link:  [Dynamic Resource Pool Calculator](http://communities.vmware.com/docs/DOC-6970)  
Link:  [VMware Infrastructure Power Documenter](http://communities.vmware.com/docs/DOC-7473)  
Link:  [ESX Automated Configuration Midwife](http://communities.vmware.com/docs/DOC-7511)  
Link:  [Add Custom Fields to VI Client with Powershell](http://www.peetersonline.nl/index.php/vmware/add-custom-fields-to-vi-client-with-powershell-samples/)  
Link:  [VMware Health Check Script](http://communities.vmware.com/docs/DOC-7430)  
Link:  [Track Datastore Free Space](http://www.peetersonline.nl/index.php/vmware/track-datastore-free-space/)  
Link:  [List disk RDMS](http://communities.vmware.com/message/1063909)  
Link:  [Find Snapshots and Send email to User](http://communities.vmware.com/docs/DOC-6980)  
Link:  [Setting Video Hardware Acceleration Level](http://www.peetersonline.nl/index.php/vmware/setting-video-hardware-acceleration-level/)