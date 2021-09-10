---
layout: single
title:  "Toolkit que Deshabilita la Distribución de Internet Explorer 8"
categories: microsoft 
tags: microsoft wsus legacy
date:   2009-01-08 05:50:23 -0400
classes: wide
---

El toolkit que liberó Microsoft permite a los usuarios y administradores configurar las PCs para que no se les instale el Internet Explorer 8 como parche de seguridad detectado por Windows Update. Recordemos que esto pasó con Internet Explorer 7 también y es importante porque si las PCs se actualizan a IE8 y luego las aplicaciones de negocio no funcionan o no son soportadas puedes tener un gran problema en la compañía.  
  
Lo bueno es que la distribución de dicho Toolkit es bien simple y hasta trae un archivo .adm para que podamos hacer dicha configuración via GPO en nuestro ambiente.  
  
El Internet Explorer 8 va a ser liberado por Microsoft como un parche de seguridad con alta prioridad, así que si no tenes este toolkit instalado y tenes configurado para que el Automatic Updates chequee e instale lo que encuentre seguramente se te va a instalar. En una compañía con WSUS tenes dos cosas a tener en cuenta, esta por un lado para las PCs y no aprobarlo en el WSUS en primera instancia. Ojo los que lo tienen en forma de aprobación automática.  
  
Aparentemente Microsoft dice que el IE8 es mucho mejor que el IE7 pero al liberarlo así no deja suficiente tiempo a las empresas a testearlo con sus aplicaciones y herramientas por eso que también ellos mismos liberaron este IE8 Blocker Toolkit.  

La pantalla de instalación será similar a la del IE7 y el mismo sale para todas las versiones de sistema operativo, por lo que seriamente te recomiendo que actualices tu sistema con el Blocker Toolkit si es que no queres que se instale automáticamente.  
  
Mas información sobre este desarrollo podes encontrarlo en el Blog del IE8 bajo el siguiente [Link](http://blogs.msdn.com/ie/archive/2009/01/06/ie8-blocker-toolkit-available-today.aspx).  

Ahora hablando del Toolkit en si que se encuentra en la página de Downloads de Microsoft viene con un script ejecutable y un archivo adm como comentaba antes. El script crea la siguiente entrada de registro en el equipo destino:  

 ```batch
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Setup\8.0  
DoNotAllowIE80
 ``` 

Si el valor es 1 está bloqueada la distribución en ese equipo, si el valor es 0 o no está definido entonces no está bloqueado el equipo de recibir el IE8. El comando puede ser ejecutado de la siguiente forma:  
  
**IE80Blocker.cmd [Nombre de PC] [/B] [/U] [/H]**
  
Si no se pone nombre de equipo correrá en forma local por lo que también se puede utilizar en forma de distribución o masiva este script. Con el /B se bloquea la distribución, con el /U se desbloquea y el /H es la ayuda.  
  
El que utilice el .ADM en sus servidores de dominio para distribuirlo por GPO va a encontrar estos parámetros, luego de cargar el archivo, en:  
  
**"Computer Configuration / Administrative Templates / Windows Components / Windows Update / Automatic Updates Blockers"**  
  
Para mas información les recomiendo que revisen el link del Blog del IE y el link para bajar el Toolkit donde podrán encontrar esta info y mas.  
  
Link:  [Download Toolkit to Disable Automatic Delivery of Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?FamilyID=21687628-5806-4ba6-9e4e-8e224ec6dd8c&DisplayLang=en)