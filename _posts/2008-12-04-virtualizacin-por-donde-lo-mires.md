---
layout: single
title:  "Virtualización por donde lo mires…"
categories: microsoft vmware
tags: microsoft vmware hyperv legacy
date:   2008-12-04 05:50:23 -0400
classes: wide
---

Como bien saben estuve escribiendo algunos artículos sobre VMware y otros sobre Hyper-V de Windows Server 2008. Obviamente no tomo partida por ninguna de las tecnologías, al contrario, analizo ambas, las pruebo, las implemento, las configuro y las uso pero no voy a defender una u otra ya que ambas tienen sus cosas buenas y malas. En esta oportunidad voy a comentar algunos artículos y noticias interesantes sobre Virtualización y otras cositas que les pueden servir para informarse como me sirvió a mi en su momento. También hay algunas cositas sobre SCVMM que es la consola de System Center para administrar máquinas virtuales, realmente muy potente y completa.  

## VMware

**Cómo Convertir un Equipo Físico a Virtual (P2V)**  
Acá les dejo un link con todos los pasos con pantallas incluídas de cómo se hace esta conversión utilizando el VMware Converter Enterprise. Para los que no lo conocen VMware Converter es la solución que VMware ofrece a sus clientes para convertir los equipos físicos en virtuales y los virtuales en virtuales (P2V y V2V). Cabe destacar que V2V es cuando tenes una máquina virtual en otra plataforma y la virtualizas a VMware.  
  
El sitio de este artículo es muy útil para todos los temas relacionados con Virtualización y así como hay uno para estas tecnologías hay para Mensajería, Seguridad, etc. Te invito a que lo visites y navegues en la tecnología que te desenvuelvas. Este tutorial es muy bueno, muy detallado y te va a ayudar en el proceso de migrar una máquina física en una virtual muy rápidamente.  
  
Link:  [P2V conversion to VMware ESX Server using VMware Converter Enterprise](http://www.virtualizationadmin.com/articles-tutorials/vmware-esx-articles/p2v-v2v/performing-p2v-conversion-vmware-esx-server-converter-enterprise.html)  
  
**VMware adquiere Trango**  
Con esta adquisición VMware toca la puerta al negocio de los dispositivos móviles. Está en el desarrollo de un nuevo hypervisor optimizado para dispositivos móviles. El nombre de este nuevo hypervisor es: VMware\'s Mobile Virtualization Platform (MVP)  
  
Existe un sin número de beneficios tanto para los que venden dispositivos móviles como para los usuarios de los mismos. Te invito a que leas esta noticia que es realmente importante para el mundo de los celulares.  
  
Link:  [VMware Acquires Trango, Brings Virtualization to Telecom Market](http://virtualizationreview.com/news/article.aspx?editorialsid=10375)  
  
**Hyper9**  
Esta es una herramienta de administración de VMware que en este momento está en etapa BETA. Es como si administráramos nuestro ambiente VM desde un entorno web y lo comparan como si fuese un Google de las VM. :)

  

## Microsoft Hyper-V

**10 ítems que tenes que saber de Hyper-V**  
Este artículo es muy bueno y completo sobre los 10 puntos o ítemes que tenes que saber sobre Hyper-V si es que estas algo perdido con el tema. Comentan sobre el hardware donde puede correr el Hyper-V. Un tema muy importante es sobre el licenciamiento de dicho producto. La verdad es un artículo muy completo así que acá te dejo el link.  
  
Link:  [10 things you should know about Hyper-V](http://blogs.techrepublic.com.com/10things/?p=431)

**SAP y su Virtualización**  
Todos sabemos que SAP es una herramienta altamente utilizada por las empresas, pero qué hay de su virtualización? Bueno acá hay un excelente informe donde SAP soporta ser virtualizado bajo Windows. Ya se sabía que SAP estaba trabajando junto a Microsoft para poder hacer una plataforma performante de virtualización. VMware ya era soportado por SAP por eso la noticia es que Hyper-V forma parte de dicha familia. También dejo un documento muy interesante sobre virtualizando SAP.  
  
Link:  [SAP on Microsoft Windows](https://www.sdn.sap.com/irj/sdn/windows)  
Link:  [Virtualization of SAP on Windows](https://www.sdn.sap.com/irj/sdn/go/portal/prtroot/docs/library/uuid/70f63258-bff1-2a10-9db6-cda6ef202bfc)

**Habilitando la Administración Remota en Hyper-V**  
Hace unos días había escrito un artículo sobre cómo habilitar la administración remota de Microsoft Hyper-V Server 2008 y todos los pasos que eran necesarios para poder lograrlo. En este sitio de MSDN vamos a conocer HVRemote que es una herramienta que va a hacer todo ese trabajo por nosotros. Se las recomiendo para que le den un vistazo y la vayan probando ya que la configuración manual es muuuy pesada.  
  
Link:  [Hyper-V Remote Management Configuration Utility](http://code.msdn.microsoft.com/HVRemote)

**Guía de Configuración de Hyper-V**  
Un documento de Microsoft muy importante a la hora de configurar Hyper-V. Explica todo lo que podemos tunear y administrar de este excelente producto.  
  
Link:  [Microsoft Hyper-V Server 2008 Configuration Guide](http://www.microsoft.com/downloads/details.aspx?FamilyId=E1E111C9-FA69-4B4D-8963-1DD87804C04F&displaylang=en)  

## System Center Virtual Machine Manager (SCVMM)

**Administrando con SCVMM y Powershell**  
Existe un excelente documento de Microsoft donde podemos aprender a administrar junto a SCVMM y Powershell. Este ultimo se volvió muy popular con Windows Server 2008 y Exchange Server 2007, pero también sirve para las máquinas virtuales entre otras tecnologías.  
  
Link:  [Managing Virtualization with SCVMM and Powershell](http://www.microsoft.com/downloads/details.aspx?FamilyID=0c3a871d-9e80-46dd-85bc-3f759f007416&DisplayLang=en&hash=7BcUW0DOgUtFarxEHIXtpwNm8iVrDtONtHEeZ2RGLoIjLrgiMMzKglkdAn2BnYDTw4NfHFVZoN2BfZRJJr3OrQ%3d%3d)