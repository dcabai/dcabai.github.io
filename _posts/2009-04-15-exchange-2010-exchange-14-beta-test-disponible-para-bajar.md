---
layout: single
title:  "Exchange 2010 / Exchange 14 BETA Test Disponible para Bajar"
categories: microsoft exchange
tags: microsoft exchange legacy
date:   2009-04-15 05:50:23 -0400
classes: wide
---

Así es, Microsoft liberó la beta para testing público de la nueva versión de **Exchange**. Hace pocos días también confirmó que el nuevo Office se llamará 2010 en vez de 14 y ahora liberó el Exchange que va a compartir el nombre 2010.  
  
Esta nueva versión tiene muchos nuevos features que te van a gustar y por lo menos para bajar esta versión y probarlos antes de que salga a producción. Además para poder estar preparados cuando realmente salga al mercado y las empresas empiecen a instalarlo.  
  
Entre los nuevos features estan:

-   Nuevas funcionalidades contra **AD RMS** que permiten segurizar mas los correos con dicha herramienta e incluso permite que los permisos de RMS se extiendan en los attach de los correos.
-   Nuevas funciones de **ruteo y transporte** de correos que permiten por ejemplo utilizar la solución de casillas Exchange hosted mientras tenes tu propio servicio instalado y que ambos convivan.
-   **Disclaimers**!!! :) Ahora soporta agregar el mensaje de disclaimers con links, imágenes, formato html, etc. Qué buena noticia no?
-   **Moderación de mensajes**, esto significa que podemos hacer una regla que todos los correos enviados a algún recipiente sean antes enviados a otra persona para que lo apruebe.
-   Mejora de **Performance** en la base de datos y en las comunicaciones.
-   Nueva forma de asignar permisos y roles a través de **Role Based Access Control (RBAC)** que cambia respecto a versiones anteriores.
-   Nuevas funciones en cuanto a **alta disponibilidad**. No va a estar mas disponible LCR ni SCC, sino que el **CCR y SCR** se fusionan para formar la única solución de alta disponibilidad que estará embebida en el mismo Exchange.
-   Nuevas opciones en el **OWA** como adjuntar mensajes dentro de mensajes o enviar SMS desde el mismo OWA.
-   Obviamente nuevas funciones de **Unified Messaging** donde podemos encontrar alertas via SMS sobre llamadas perdidas o el voice mail protegido.
-   Nuevas opciones en la consola de administración como **Organizational Health**, **Command logging**, etc.
-   Administración remota del Exchange a través de **PowerShellv2** y **WinRM2.0**.

Creo que son algunos features muy interesantes y vale la pena instalarlo y probarlo. En el próximo artículo presentaré la instalación del mismo para que puedan ver los pasos y algunas diferencias con Exchange 2007.  
  
Los requerimientos de Hardware son muy parecidos a los de Exchange 2007, salvo que ahora requiere un poco mas de memoria para el Exchange mismo, pero el requerimiento por casilla es el mismo. En cuanto a Software requiere Windows Server 2008, .NET Framework 3.5, WinRM 2.0 CTP3, PowerShellv2 CTP3 y ASP.NET AJAX 1.0.  
  
Los roles de IIS de Win2K8 que se requieren son:
```batch
ServerManagerCmd -i Web-Server
ServerManagerCmd -i Web-ISAPI-Ext
ServerManagerCmd -i Web-Metabase
ServerManagerCmd -i Web-Lgcy-Mgmt-Console
ServerManagerCmd -i Web-Basic-Auth
ServerManagerCmd -i Web-Digest-Auth
ServerManagerCmd -i Web-Windows-Auth
ServerManagerCmd -i Web-Dyn-Compression
ServerManagerCmd -i NET-HTTP-Activation
ServerManagerCmd -i RPC-over-HTTP-proxy
```

Esta es una buena opción para que empieces a probar el **Exchange 2010** y nos cuentes tu experiencia.

Link:  [Download Microsoft Exchange Server 2010 Beta](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=1898ed2c-2f88-48ac-824e-d3d20fad77d7)  
Link:  [Exchange 2010 Home](http://www.microsoft.com/exchange/2010/en/us/default.aspx)  
Link:  [Exchange 2010 Technet Home](http://technet.microsoft.com/en-us/library/bb124558(EXCHG.140).aspx)  
Link:  [Foro Exchange 2010 Oficial](http://social.technet.microsoft.com/Forums/en-US/exchange2010/threads)