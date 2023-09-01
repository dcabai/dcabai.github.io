---
layout: single
title:  "Windows Server 2008 - Nuevos Features"
categories: microsoft 
tags: microsoft windows server hyperv activedirectory legacy
date:   2007-09-14 05:50:23 -0400
classes: wide
---
Como ya saben esta versión llega con suerte el 27 de Febrero, la RC1 estaría saliendo a fin de este mes, ahora bien, vamos a lo importante. Qué trae esta nueva versión de Windows? Posee grandes mejoras con respecto a las versiones anteriores? Nos puede beneficiar en nuestro negocio o plataforma? Espero que en este post salgan algunas de estas dudas. Microsoft publicita en sus campañas de marketing ciertos temas como que son la base de este nuevo sistema operativo. Los mismos se clasifican en: Web, Virtualización, Seguridad y Solidez.

Empecemos por lo básico, las comunicaciones. Hoy en día son críticas para las organizaciones ya que hay que estar bien posicionado para poder estar al día en el mercado global. Los usuarios tienen que poder acceder a la red desde cualquier parte del mundo, a sus archivos, correo, etc y esta comunicación debe ser segura. **Mobilidad**. Estas mejoras ya las vimos en Windows Vista, lo cual ahora también trae Windows Server 2008. Nosotros los Administradores de TI podemos enviar mas configuraciones para equipos conectados y wireless de manera centralizada, podemos usar políticas (GPO), scripts, etc y configurar diferentes escenarios protegidos.

Tanto Windows Server 2008 como Windows Vista incluyen una nueva versión del TCP/IP stack conocido como **Next Generation TCP/IP stack**. Lo que hicieron fue un rediseño completo de las funcionalidades del IPv4 y del IPv6 logrando la performance y necesidades del día de hoy. No es mi intención hacer comentarios bien técnicos pero si estas mas interesado en este link de Microsoft hay mas información técnica: [Next Generation TCP/IP Stack Web page](http://www.microsoft.com/technet/network/tcpip/default.mspx)

La idea es tener claro que hay muchas mejoras a nivel conectividad tanto para equipos conectados a la red física como wireless, incluso a nivel seguridad con la implementación de la nueva versión de Windows Firewall que ya vimos en Windows Vista, junto a su consola de administración de políticas mejorada.

Se cree que con esta versión de Windows los clientes van a tener muchas mas razones para migrar que las que tenía de 2000 a 2003. Los nuevos features son bárbaros, incluso me sorprendía cuando los probaba y testeaba en las betas del mismo. Por ejemplo, uno de los nuevos features en Windows Server 2008 es la habilidad de poder **auto-solucionar problemas NTFS en background**. Si, como lo leíste, si se detecta una corrupción en alguna parte de la estructura de datos, hay un proceso que corre en background que se ocupa y soluciona ese problema localizado sin necesidad de bajar el equipo o reiniciarlo para correr un chkdsk. :D

El agregado de **BitLocker** para encriptar todo el disco también es un feature notable. Verificar bien cómo deben estar creadas las particiones antes de habilitarlo, ya que después puede ser tarde.

Se mejoró el **procedimiento de Shutdown** (Apagado) del equipo para que sea lo mas limpio posible para las aplicaciones, eso si, puede demorar un poco mas pero nuestras aplicaciones lo van a agradecer.

**Network Access Protection (NAP)** / Protección de Acceso a la Red. Basicamente lo que hace es habilitar políticas a la red para que no se pueda conectar cualquier equipo sino que pase por un filtro, por ejemplo nivel de Service Pack. [Cisco](http://www.cisco.com/) actualmente soporta la utilización de NAP. 

**Network Policy and Access Service (NPAS)** / Servicio de Accesos y Políticas de Red, es el servicio que maneja todas las políticas de seguridad de red.

Ahora el sistema soporta la creación de sesiones en paralelo. En versiones anteriores de Terminal Server por ejemplo, las sesiones eran seriales y si se conectaban todos los usuarios a la misma hora se producía lentitud y cuello de botella. Ahora Windows Server 2008 soporta el procesamiento de hasta 4 sesiones simultáneas y más si es que tiene más de 4 procesadores. Windows Vista ya posee esta tecnología para los Media Center por ejemplo.

Llegó el **SMB2** junto a Longhorn. La vida del SMB era bastante corta y mas en sistemas que requerían performance. Se cree que con SMB2 es un 30 o 40 veces más rápido en performance de sistema con media servers, los cuales tienen archivos de gran tamaño.

**Address Space Load Randomization (ASLR)**, es un feature que agrega seguridad al sistema operativo y ya se encuentra activo en Vista. Lo que hace es que no se pueda cargar el mismo driver de sistema en el mismo lugar en la memoria, de esta manera genera un random (aleatorio) y los malware por ejemplo no pueden ubicar un determinado espacio en memoria con el que hacían daño a un equipo.

**Windows Hardware Error Architecture (WHEA)**, con este feature lo que hizo Microsoft fue standarizar los errores y resportes de error, haciendo que tanto orientados a hardware como de software incluso de terceros puedan aprovechar esta standarización y centralizar los errores de una sola manera.

**Virtualización de Windows Server** es uno de los features que mas afecta a las empresas en cuanto a lo económico ya que lo que se ahorra una compañía con la consolidación de servidores es un número a tener en cuenta. Tal vez este mercado sea liderado por VMWare pero Microsoft se impuso fuertemente ya que es a donde apunta el futuro de las consolidaciones y ahorros.

**PowerSell...(cmdlets)** si, una de las herramientas de las que mas debemos haber escuchado hablar. Esta herramienta de administración es parte del sistema operativo y puede suplementar completamente la administración gráfica. Es muy potente, robusta, sencilla de utilizar y generar scripts para automatizar tareas.

**Server Core**. Este es un cambio radical para Microsoft. Ahora soporta servidores libres de interfaz gráfica, osea con baja carga de procesamiento y pueden ser administrados desde cualquier terminal tanto a través de PowerShell o bien de herramientas administrativas gráficas. Siempre pensamos, para qué un servidor requería drivers 32bit de color por ejemplo si nunca íbamos a correr aplicaciones de usuario. Este modo es opcional y soporta casi todos los roles del sistema operativo. Incluso se pueden tomar las consolas de los Core Servers a través de RDP en el puerto 3389.

El servicio de **Cluster (Failover Clustering)** también sufrió algunos cambios y mejoras. La configuración es simple, se puede enviar por script y se pueden agrupar los equipos para compartir carga de manera sencilla.