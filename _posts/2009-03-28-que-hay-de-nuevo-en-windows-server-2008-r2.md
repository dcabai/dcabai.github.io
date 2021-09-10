---
layout: single
title:  "Qué hay de nuevo en Windows Server 2008 R2?"
categories: microsoft 
tags: microsoft windows server hyperv activedirectory legacy
date:   2009-03-28 05:50:23 -0400
classes: wide
---
Ya había hecho algunos comentarios sobre las novedades en cuanto al servicio de Hyper-V para la nueva versión de Windows Server 2008. Pero este sistema operativo ofrece otros servicios que también sufren modificaciones o nuevos features y la idea era comentar algunos de ellos porque estan muy buenos y si hoy estas usando Windows Server 2008 en tu ambiente seguro vas a querer actualizarte al R2. Si en cambio todavía tenes 2003, actualizate YA!, me lo vas a agradecer.  
  
**Active Directory PowerShell cmdlets**: Como el nombre lo dice, son nuevos cmdlets administrativos en PowerShell para Active Directory.  
  
**Active Directory Best Practice Analyzer**: Por fin un buen BPA para Active Directory completo que nos puede decir donde está el error de configuración.  
  
**Active Directory Web Services (ADWS)**: Es un nuevo servicio de un Domain Controller que sirve como interfaz web entre las instancias que corren de AD, LDS, etc. Si este servicio se para o se deshabilita, ya que se instala por defecto, algunas instancias como el Administrative Center o el PowerShell module no funcionaran.  
  
**Active Directory Administrative Center**: Ahora podemos administrar el Active Directory desde una nueva GUI mucho mejor que el anterior ADUC que sigue estando, pero esta nueva consola basada en scripts PowerShell nos da la oportunidad de administrar el AD centralizadamente de forma simple para las tareas rutinarias.  
  
**Offline Domain Join**: Ahora vamos a poder programar las PCs para que ingresen al dominio sin necesidad de realmente hacerlo y cuando la PC inicie por primera vez se va a agregar sola. Esto sirve para deploys masivos.  
  
**Active Directory Recycle Bin**: Obviamente si traducimos el nombre sabemos para que sirve. Cuántas veces vemos que eliminan cuentas de usuario y después tienen que hacer un restore para poder recuperarlo? Ahora podemos hacerlo de una manera mucho mas simple ya que queda en una papelera de reciclaje de AD. Acá les dejo un gráfico que muestra la vida de un objeto en el Active Directory con el Recycle Bin activado.

![image-center](/assets/images/QuhaydenuevoenWindowsServer2008R2_AE77/image.png  "Active Directory Recycle Bin"){: .align-center}

**Active Directory Certificate Services (AD CS):** ahora permite una implementación mas flexible de una infrasestructura PKI, reduce administración y soporta NAP.  
  
**Windows AppLocker**: Este features es nuevo tanto en Windows Server 2008 R2 como en Windows 7 reemplaza las políticas de restricción de Software. Sigue basado en reglas que uno puede exportar e importar.  
  
**Biometrics**: Windows 7 soporta habilitar biometrics para la autenticación como por ejemplo a través de un lector de huellas digitales y poder elevar privilegios con el UAC. Esta configuración puede ser enviada por GPO.  
  
**DNS**: Siiii algo nuevo en el DNS también, ahora soporta Domain Name System Security Extensions (DNSSEC). Ahora con Windows Server 2008 R2 podemos firmar y hostear zonas firmadas-DNSSEC y darle seguridad al ambiente. Soporta los registros DNSKEY, RRSIG, NSEC y DS.  
  
**Failover Clusters**: Algunas mejoras en el proceso de validación de un cluster nuevo o existente. Las mejoras de Cluster con Virtual Machines a través de Hyper-V que ya había comentado antes. La interfaz PowerShell para la administración del servicio, y mejoras en la posibilidad de migrar las configuraciones de un cluster a otro.  
  
**Hyper-V**: Ya lo comenté mas en detalle antes, pero está Live Migration, Enhanced Processor Support, Enhanced Networking Support, Dynamic Virtual Machine Storage, etc.  
  
**Group Policy**: No hay muchos cambios, si a nivel administrativo gracias a los Cmdlets de PowerShell, algunos ítems nuevos de Group Policy Preferences, mejoras en las Starter GPO’s, y otros administrative settings adicionales.  
  
**Network Access Protection (NAP)**: Multi-Configuration SHV que simplemente permite la configuración de múltiples System Health Validators (SHV). En cuanto al cliente NAP tiene algunas mejoras para Windows 7.  
  
**Network Policy Server (NPS)**: La administración de los templates y los templates de NPS son uno de las nuevas características. Esto permite generar la configuración para un determinado servicio o server y reutilizarlo en otro equipo o en el mismo equipo local. También hay mejoras en el accounting del RADIUS que permite configurar un SQL para guardar los logs.  
  
**Networking**: Hay varias mejoras en cuanto a networking tanto para Windows Server 2008 R2 como para Windows 7. Algunas de ellas son, Direct Access que permite conectarte a la red de tu compañía sin necesidad de iniciar una VPN antes. VPN Reconnect, que simplemente si se cayó la conexión de VPN la vuelve a iniciar. BrandCache que como el nombre lo dice, hace un caché de archivos y webs a través de una WAN. URL QoS con el que podemos definir prioridad según la URL desde donde se origine el tráfico. Multiple active firewall profiles, con el que cambiará las reglas de firewall según la red a la que estemos conectados.  
  
**Server Manager**: Podemos administrar servidores remotamente desde la consola de Server Manager. Best Practice Analyzer (BPA) para determinados roles y features. Nuevos PowerShell Cmdlets propios de Server Manager como por ejemplo Add-WindowsFeature. WSUS está disponible como rol desde el Server Manager. Y obviamente la posibilidad de agregar o configurar los nuevos features comentados acá.  
  
**Web Server (IIS)**: Este también sufrió grandes cambios, IIS 7.5 ahora tiene nuevos features y mejoras en WebDAV y FTP, los módulos de administración, Best Practice Analyzer (BPA), PowerShell, Hostable Web Core, FastCGI y .NET en Server Core. En el link del final del artículo podes leer todas las características completas.  
  
**PowerShell**: Este si que tuvo cambios. Obviamente nuevos Cmdlets, administración remota, Windows Integrated Scripting Environment (ISE) que es una interfaz gráfica para poder armar scipts complejos con PowerShell. Background Jobs permite ejecución de trabajos en el background como lo dice su nombre, Debugger con el que podremos hacer un debug de las funciones o scripts que armemos, Eventos, Funciones Avanzadas, Internacionalización, etc.  
  
**Windows Security Auditing**: Mejoras en cuanto a la auditoría donde ahora ofrece mucho mas detalle. Muchas mas políticas de auditoría para configurar que antes a través de GPOs o políticas locales. Nuevos SACLs y ACEs que van a ayudar a hacer tu vida mas fácil.  
  
**Remote Desktop Services**: Este si que es largo de comentar. Para empezar sabemos que cambió el nombre obviamente del anterior Terminal Services a Remote Desktop Services. Muchísimas mejoras de performance en la experiencia del usuario, compatibilidad con Windows Installer RDS, administración de la caché de los perfiles de usuarios roaming. No soporta mas el descubrimiento automático de servidores de licencias, la administración de CALs, mejoras en cuanto a la parte de networking y WAN, etc. También se integra con Hyper-V para brindar RemoteApp y RemoteDesktop a las máquinas virtuales. Remote Desktop Client 7.0 soporta Aero en las sesiones de Windows 7 y Windows Server 2008 R2.  
  
Creo que con todo esto tenes un panorama general de las nuevas funciones, ahora sólo queda probarlas y ver si podes implementarlas en tu ambiente. Te dejo el link completo de Technet con el detalle de cada uno de estos servicios así podes leer mas a fondo el que mas te interese.  
  
Link: [What’s New in Windows Server 2008 R2 (Beta)](http://technet.microsoft.com/en-us/library/dd349801.aspx)