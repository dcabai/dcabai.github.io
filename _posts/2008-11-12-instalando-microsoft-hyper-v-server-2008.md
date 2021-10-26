---
layout: single
title:  "Instalando Microsoft Hyper-V Server 2008"
categories: microsoft 
tags: microsoft hyperv legacy
date:   2008-11-12 05:50:23 -0400
classes: wide
---

Estoy dedicandole algo de tiempo a la virtualización ya que creo que es hacia donde apunta la tecnología de hoy en día. Estoy publicando algunos artículos sobre VMware ahora voy a publicar la instalación de Microsoft Hyper-V Server 2008.  
  
La idea es comentar los pasos de instalación, con qué nos encontramos, el tiempo de la misma y qué fue necesario hacer como configuración inicial para luego en otro artículos comentarles sobre la administración remota de este equipo.  
  
En principio para los que no conocen Hyper-V es el rol de virtualización de Windows para competir con servicios como VMware y Citrix XenServer. En particular esta versión de Microsoft Hyper-V Server 2008 es una versión limitada que no requiere licencia que ejecuta una versión de Windows Server Core con el rol de Hyper-V instalado y sin muchas mas opciones de servicio. Vamos a ver cuánto se demora la instalación, qué interacción inicial es requerida y cuánto pesa la misma para luego compararla con otras soluciones similares.  
  
El equipamiento utilizado para la prueba es un servidor DELL PowerEdge 2950 y conectados a través de una placa DRAC 5 y un browser. Esto lo comento por los colores de las ventanas (feos).  
  
Al introducir el DVD la primer pantalla de instalación te pregunta el idioma, teclado, etc. Luego sólo tenemos el botón de Install Server que al presionarlo seguimos adelante.  

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image.png){: .align-center}

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image3.png){: .align-center}
  
Hasta acá seguimos fácil, aceptamos la licencia y hacemos click en “Custom” para la instalación del servidor.  
 
![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image6.png){: .align-center}

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image9.png){: .align-center}
 
Luego viene la selección del disco donde lo vamos a instalar. Podemos crear las particiones que querramos, formatearlas, etc. Esto va a criterio y disponibilidad de cada uno y al continuar ya empieza la copia de los archivos para su instalación.  

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image12.png){: .align-center}

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image15.png){: .align-center}
  
Al finalizar la instalación reinicia el equipo y la posterior pantalla que vamos a ver es la del inicio de sesión como muestro en la imagen. Al iniciar sesión por primera vez con usuario Administrator y sin contraseña nos va a pedir que la cambiemos por una contraseña válida. Obviamente inicia con el Firewall encendido y con el rol de Hyper-V instalado y activo.  

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image18.png){: .align-center}

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image21.png){: .align-center}
  
  
### Tiempo de Instalación: 17 minutos - Espacio Ocupado en disco: 2.5 Gb  

Creo que la instalación fue bastante rápida y la interacción fue bien mínima, pero todavía no configuramos nada localmente y remotamente no se puede hacer nada hasta habilitarlo en el mismo equipo. Por ejemplo, al iniciar la sesión nos vamos a encontrar con una ventana parecida a la siguiente donde vemos el nombre del equipo, el dominio al que pertenece y donde podemos modificar algunos parámetros básicos. Atrás está la ventana de CMD para poder administrar el servidor con líneas de comando. 

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image24.png){: .align-center} 
  
Si ejecutamos el comando **oclist** para ver los roles que tiene instalados el equipo vamos a ver que el único es **Microsoft-Hyper-V**. El resto no está instalado y si lo vemos mas en detalle podemos apreciar la mínima cantidad de roles disponibles para instalar y los que si están cómo estan asociados a Hyper-V. Desconozco quien instalará el BitLocker en un Hyper-V Server pero está disponible. :)  

![image-center](/assets/images/InstalandoMicrosoftHyperVServer2008_F1F2/image_3.png){: .align-center}
  

Todo muy bonito pero qué debo hacer para poder empezar a trabajar con este equipo? Localmente mucho no puedo administrar por ende qué tengo que hacer para poder hacerlo remotamente?  
  
En principio si queremos dejar el Firewall activado en el servidor tenemos que habilitar ciertas reglas. Siempre está la opción de deshabilitar el Firewall del Server Core que lo hacemos con el siguiente comando:  

```batch  
netsh firewall set opmode disable  
```  
Si sólo queremos habilitar la administración del Firewall remotamente desde una consola de otro servidor podemos ejecutar el siguiente comando:  
 ```batch 
netsh advfirewall set currentprofile settings remotemanagement enable  
 ``` 
El equipo por defecto no responde al ping/icmp, si queremos habilitar el ping en un Server Core debemos ejecutar el siguiente comando:  
```batch  
netsh firewall set icmpsetting 8  
``` 
Sino podemos hacerlo desde la consola gráfica remotamente ya que la habilitamos en el comando anterior. Lo mismo para algunos de los comandos que se van a comentar mas adelante.  
  
Hay otros comandos a tener en cuenta para la habilitación del RDP del Servidor con Server Core. Todos estos comandos son de Windows Server Core, independientemente si es la versión Hyper-V o la completa sirven para ambas.  
  
Para verificar cómo está configurado el servicio de RDP y ver si nos podemos conectar desde un cliente de Terminal ejecutamos el siguiente comando:  
 ```batch 
cscript C:\Windows\System32\Scregedit.wsf /ar /v  
```
En caso de que el resultado sea 0 (cero) significa que ya está habilitado. Si la respuesta es 1 (uno) significa que actualmente está deshabilitado. Para poder habilitarlo ejecutamos el siguiente comando:  
 ```batch
cscript C:\Windows\System32\Scregedit.wsf /ar 0  
```
Si queremos conectarnos desde clientes que no tienen la nueva versión del cliente de Terminal puede que falle porque por defecto viene habilitado con Seguridad elevada. Para poder deshabilitar ese feature podemos ejecutar el siguiente comando:  
```batch
cscript C:\Windows\System32\Scregedit.wsf /cs 0  
  ```
Hasta ahora venimos tirando un comando atrás de otro para el RDP pero no lo habilitamos en el Firewall. Como comenté antes si ya lo hacemos via GUI remota es mas sencillo, sino localmente podemos ejecutar el siguiente comando para habilitarlo.  
```batch  
netsh advfirewall firewall set rule group="Remote Desktop" new enable=yes  
  ```  
Hasta ahí configuramos lo relacionado al firewall local y el acceso via RDP para poder administrar el Server Core localmente. Todavía no habilitamos la administración desde la consola remota de Hyper-V. Obviamente que no se puede iniciar dicha consola localmente pero si se puede remotamente en otro Windows Server 2008 o en un Windows Vista que comentaré en el próximo artículo.  
  
Para poder habilitar la administración remota es necesario ejecutar dos comandos localmente en el servidor de Hyper-V, uno para la habilitación del WMI a través del Firewall que si lo deshabilitamos no hace falta y otro para habilitar a los usuarios o grupos de administración a la conexión DCOM.  
```batch    
netsh advfirewall firewall set rule group="Windows Management Instrumentation (WMI)" new enable=yes  
net localgroup "Distributed COM Users" /add domain/user  
  ```   
Si no ejecutamos dichos comandos seguramente les de “Access Denied” cuando quieran conectarse desde otro servidor con Windows Server 2008. Aquí terminamos la instalación del servicio localmente en el Hyper-V, el resto de la configuración se puede hacer remota desde Windows Vista o desde otro Windows Server 2008.  
  
Link: [Download Microsoft Hyper-V Server 2008](http://www.microsoft.com/downloads/details.aspx?FamilyId=6067CB24-06CC-483A-AF92-B919F699C3A0)