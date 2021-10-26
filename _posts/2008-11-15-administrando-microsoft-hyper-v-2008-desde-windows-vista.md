---
layout: single
title:  "Administrando Microsoft Hyper-V 2008 desde Windows Vista"
categories: microsoft 
tags: microsoft hyperv legacy
date:   2008-11-15 05:50:23 -0400
classes: wide
---

En un artículo anterior comentamos los pasos para instalar Microsoft Hyper-V Server 2008. También comenté algunos de los pasos necesarios para habilitar la administración remota y deshabilitar el firewall o bien configurarlo como lo necesitemos. Tal vez si está en la misma LAN no dejemos el firewall habilitado o tal vez si dependiendo de la seguridad de nuestra empresa.  
  
Algunos de los comandos necesarios para poder administrarlo con el firewall activado tal vez se repitan en este artículo pero como son necesarios para poder administrar remotamente el servidor de Hyper-V desde un Windows Vista los vuelvo a comentar.  
  
Recordemos que si queremos deshabilitar el firewall en el servidor de Hyper-V debemos ejecutar el siguiente comando:  
  
```batch
netsh firewall set opmode disable
```
  
Si este es tu caso entonces muchas otras configuraciones de acceso no serán necesarias pero sino vas a tener habilitar acceso a DCOM y WMI como lo comento mas abajo.  
  
Empecemos del lado del cliente Windows Vista ya que necesitamos instalar algunas herramientas para poder tomarle control y además debemos hacer algunas configuraciones adicionales.  
  
Primero debemos instalar las **RSAT** (Remote Server Administration Tools). Abajo estan todos los links para bajar lo que necesitemos. Una vez instaladas no vamos a ver ningún nuevo ícono, para eso debemos habilitarlas desde el Panel de Control. Ahí vamos a Programs and Features y seleccionamos Turn on or off Windows Features. Ahí vamos a ver unas ventanas como las siguientes:  
 
 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image.png){: .align-center}
   
 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image3.png){: .align-center}
 
Ahí buscamos las Remote Server Administration Tools instaladas y vamos a ver que podemos instalar las herramientas de administración remota para casi todo, excepto Hyper-V…mmm justo lo que necesitábamos. Para esto hay que instalar un adicional que justamente es para administrar Hyper-V, es que las herramientas salieron antes que el Windows Server 2008 definitivo con el rol de Hyper-V. Nuevamente abajo está el link necesario. Luego de instalarlo y agregar el feature si veremos el ícono de Hyper-V Manager.  
 
 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image6.png){: .align-center}

 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image9.png){: .align-center}
 
   
Al abrir la consola de administración veremos algo como la imagen siguiente. Desde aquí podremos conectarnos al servidor o servidores con Hyper-V de nuestro ambiente.  

 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image12.png){: .align-center}  
  
  
Si en el servidor de Hyper-V tenemos el firewall deshabilitado entonces basta con conectarnos al servidor para poder administrarlo, configurarlo, crear los discos, redes y máquinas virtuales (VM’s).  
  
 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image111.png){: .align-center}


Ojo, esta consola es la de administración y es bastante básica, sirve para administrar el rol y las VM’s creadas pero no es como la consola SCVMM donde tiene muchas mas funciones y capacidades. Si buscas una consola de Hyper-V completa entonces te sugiero que recurras a System Center Virtual Machine Manager 2008 (SCVMM).  
  

### Configuraciones para Acceder Remotamente

Algunos de los comandos necesarios del lado del servidor en la consola ya los comenté en el artículo anterior así que te recomiendo que lo re-leas. En especial los comandos de netsh para habilitar el acceso WMI en el Firewall del servidor y para habilitar el acceso DCOM al mismo.  
  
Adicionalmente a eso debemos autorizar a nuestro usuario a administrar el rol de Hyper-V. Esto lo hacemos ejecutando el  **azman.msc**  desde Start –> Run. Aquí vamos a abrir el Authorizarion Manager y debemos ir a “Open Authorization Store”. Ahí nos va a preguntar la ruta al archivo XML con la configuración, esto debemos apuntarlo a  

```batch
\\<servidor-hyper-v>\C$\ProgramData\Microsoft\Windows\Hyper-V\initalstore.xml  
```  
 ![image-center](/assets/images/AdministrandoMicrosoftHyperVdesdeWindows_9E4C/image1.png){: .align-center}

En la consola debemos ir a  **Hyper-V Services**  y luego sobre  **Role Assignments**. Ahí hacemos click derecho sobre  **Administrator**, y seleccionamos  **Assign Users and Groups**. Ahí tenemos para elegir entre usuarios de Active Directory o usuarios de Windows. Elegimos lo deseado a quien querramos darle acceso desde una consola remota y luego hacemos click en Ok y podemos cerrar la consola de Authorization Manager.  
  
Luego debemos darle permisos al WMI del servidor. Para esto podemos hacerlo desde la consola de Computer Management y en Services and Applications hacemos botón derecho sobre WMI Control –> Propiedades. En la solapa de Seguridad debemos asignar permisos sobre el CIMV2 namespace y sobre el virtualization namespace.  
  
Los permisos que asignemos debemos asegurarnos de hacerlo para ese namespace y para los subnamespaces. Los permisos que tenemos que seleccionar son  **Remote Enable**  para ambos namespaces y para ese objeto y los subobjetos.  
  
Hacemos click en Ok de todas las ventanas abiertas y con eso habremos asignado los permisos para la administración remota. Recuerda que en el artículo anterior hay otros pasos necesarios para ser ejecutados sobre el servidor de Hyper-V, estos son pasos a ejecutar remotamente. También ten en cuenta que si deshabilitas el firewall del Hyper-V Server entonces todo esto no es necesario.  
  
Link:  [Microsoft Remote Server Administration Tools for Windows Vista (KB941314)](http://www.microsoft.com/downloads/details.aspx?FamilyId=9FF6E897-23CE-4A36-B7FC-D52065DE9960&amp;amp;displaylang=en&displaylang=en)  
Link:  [Hyper-V Remote Management Update for Windows Vista (KB952627)](http://www.microsoft.com/downloads/details.aspx?familyid=BF909242-2125-4D06-A968-C8A3D75FF2AA&displaylang=en)  
Link:  [Microsoft Technet Hyper-V](http://technet.microsoft.com/en-us/library/cc753637.aspx)