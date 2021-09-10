---
layout: single
title:  "System Center Virtual Machine Manager 2008 R2 Beta (SCVMM)"
categories: microsoft 
tags: microsoft windows scvmm hyperv legacy
date:   2009-03-16 05:50:23 -0400
classes: wide
---
Ya está disponible para probar la beta de la versión R2 del System Center Virtual Machine Manager 2008. El mismo está disponible a través del sitio de Microsoft Connect y una vez que inicias sesión debes completar un cuestionario donde evalúa si puedes participar de la beta o no. Si estas calificado para hacerlo podrás acceder a descargar el producto y enviar feedback a Microsoft. Está el producto para instalar como también un VHD con el equipo ya instalado y preparado para bajarlo y empezar a probar el software.  
  
Qué es lo nuevo que viene con SCVMM R2?  
**  
Live Migration**: Si bien ya había comentado algo sobre esto, permite mover VMs entre hosts sin que haya pérdida de servicio. Esto significa que la VM está corriendo perfectamente en el Hyper-V “A” y la movemos al “B” sin que los usuarios sufran un corte en el servicio.  
  
**Clustered Shared Volume**: Sirve para poder habilitar el Live Migration y elimina el requerimiento anterior de una LUN por VM simplificando la administración de nuestra SAN.  
  
**Hot Add/Remove Storage**: Permite agregar o remover Storage iSCSI o discos virtuales (VHD) en nuestra infraestructura virtual sin necesidad de apagar la VM, por eso el concepto de “Hot” o en caliente.  
  
**Networking Optimizations**: Virtual Machine Queue (VMQ) y Chimney son dos nuevas tecnologías agregadas para mejorar la performance de red y bajar la carga de CPU para dicha tarea.  
  
Si bien no puedo mostrar ninguna imagen ni video del producto por razones de seguridad del sitio de Microsoft Connect, les cuento que los nuevos features están muy buenos y no veo la hora de que salga al mercado para poder utilizarlos en ambientes productivos.

Link: [Inscribirse en la Beta](https://connect.microsoft.com/SelfNomination.aspx?ProgramID=3021&pageType=1&SiteID=799)