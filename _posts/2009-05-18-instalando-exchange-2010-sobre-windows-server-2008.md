---
layout: single
title:  "Instalando Exchange 2010 sobre Windows Server 2008"
categories: microsoft exchange
tags: microsoft exchange legacy
date:   2009-05-18 05:50:23 -0400
classes: wide
---

La idea es comentar la instalación para la prueba del **Exchange 2010 Beta** y así mostrar algunos features. No voy a revelar nada que no se pueda ya que la Beta es pública. Primero voy a comentar los requerimientos y pasos para instalar el Windows Server 2008 que necesitamos para el Exchange o bien los requisitos del mismo servidor de Exchange.  
  
En este caso el equipo es el mismo ya que es una máquina virtual y el objetivo es simplemente testing, pero en producción no lo instalen en el mismo servidor, para ese tipo de soluciones deben adquirir SBS o EBS que vienen preparados para dicha carga de trabajo y configuraciones sobre el equipo.  
  
Primero debemos instalar un Windows Server 2008 para que funcione como Domain Controller de nuestra red o bien podemos hacer que sea el mismo equipo que vamos a usar para Exchange 2010, pero sólo en modo de testing o laboratorio, no en un ambiente de producción. Una vez que instalamos el OS proseguimos a la configuración de los roles.  

 ```batch 
ServerManagerCmd –i ADDS-Domain-Controller  
  ```
  
Con ese comando agregamos el rol de Domain Controller, también lo podemos hacer desde la interfaz gráfica pero desde la de texto es mas exacto. Luego de agregar el rol hace falta correr el **dcpromo** para poder configurar el rol de Domain Controller y así convertirlo en su totalidad. En ese asistente nos va a instalar el rol de DNS Server si es que no está instalado ya que lo requiere. Luego reiniciamos el servidor y ya tenemos nuestro Domain Controller listo para operar. Si es el primer y único DC de nuestro ambiente de pruebas, automáticamente lo va a configurar como Global Catalog. De lo contrario debemos tener un Global Catalog por cada site que instalemos un Exchange. En esto se comporta igual que con Exchange 2007.  
  
Las herramientas administrativas de AD y DNS las instala automáticamente cuando agregamos los roles así que no debemos preocuparnos por eso. Incluso nos agrega la consola para administrar las políticas de dominio (GPMC). Revisamos los eventos de Windows y si está todo ok proseguimos con la instalación.  
  
El Exchange requiere tener instalado el IIS o Web Server así que podemos ejecutar el siguiente comando para instalar todos los requisitos del IIS.  
 ```batch
ServerManagerCmd –i Web-Server Web-ISAPI-Ext Web-Metabase Web-Lgcy-Mgmt-Console Web-Basic-Auth Web-Digest-Auth Web-Windows-Auth Web-Dyn-Compression NET-HTTP-Activation RPC-over-HTTP-proxy
```
  
![image-left](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image.png "ServerManagerCmd IIS"){: .align-left}

En si es el comando para agregar roles o features y luego estan todos los roles separados por un espacio. Obviamente que al agregar estos roles nos va a agregar muchos otros mas que son requeridos por estos así que no nos asustemos cuando veamos una lista mucho mas grande al finalizar la instalación.  
  
Este rol es muy importante que esté completo ya que es 100% utilizado por el Exchange como en versiones previas así que controlemos que quede todo bien instalado y que el mensaje final sea OK.  
  
![image-left](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_3.png "Server Manager Roles Overview"){: .align-left}
Si nos paramos sobre Roles dentro de Server Manager GUI vamos a ver algo parecido a lo que se muestra en la imagen.  
  
Hasta ahora sólo agregamos roles y features de Windows Server 2008 y esto es lo que nos quedó y desde acá podemos administrarlo. Ahora nos queda instalar el software adicional de Microsoft que es requisito de Exchange 2010. Mas abajo nombro el soft requerido junto con el link para poder descargarlo.  
  
El software requerido por Exchange 2010 es el siguiente y debe ser descargado e instalado en el equipo previamente a la instalación de Exchange.  
  
Link: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?FamilyID=333325fd-ae52-4e35-b531-508d977d32a6&DisplayLang=en)  
Link: [Windows PowerShell V2 Community Technology Preview 3 (CTP3)](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=c913aeab-d7b4-4bb1-a958-ee6d7fe307bc)  
Link: [ASP.NET AJAX 1.0](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=ca9d90fa-e8c9-42e3-aa19-08e2c027f5d6)  
Link: [WinRM 2.0 CTP3](http://go.microsoft.com/fwlink/?linkid=131971)  
Link: [2007 Office System Converter: Microsoft Filter Pack](http://go.microsoft.com/fwlink/?LinkId=123380)  
  
Una vez que concluímos con dichas instalaciones continuamos con la ejecución del exe descargado de Microsoft que en principio va a descromprimir los instaladores de Exchange 2010. Una vez que esté todo descomprimido debemos ejecutar **Setup.exe** y abrirá la siguiente pantalla.  
  
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_4.png "Exchange 2010 Setup"){: .align-center}  
  
Como ven, los requisitos de Software ya los tengo instalados, pero si no estuviesen debería hacerlo. Como estamos listos para continuar hacemos click en el paso **4: Install Microsoft Exchange**. Luego los pasos que va a ir mostrando son bastantes intuitivos.  
  
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_5.png "ExSetup"){: .align-center}    ![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_6.png "ExSetup"){: .align-center}      
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_7.png "ExSetup"){: .align-center}      ![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_8.png "ExSetup"){: .align-center}      
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_9.png "ExSetup"){: .align-center}      ![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_10.png "ExSetup"){: .align-center}      
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_11.png "ExSetup"){: .align-center}      ![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_12.png "ExSetup"){: .align-center}      
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_13.png "ExSetup"){: .align-center}      ![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_14.png "ExSetup"){: .align-center}      
  
Muy bien, ya tenemos la instalación terminada y nuestro servidor de Exchange 2010 arriba. Esta es una instalación bien básica con los tres roles en el mismo equipo, sin packs de idioma adicionales y en el mismo servidor que el Domain Controller. Cada uno puede hacer su propio laboratorio, éste tenía la intención de hacer la instalación y ver las herramientas administrativas por arriba. También cabe destacar que todo el laboratorio fue instalado en una máquina virtual VMware ejecutándose en un VMware Player dentro de un Windows Vista. :) Un poco kamikaze no? pero funcionó y tuvo su fin que era el ver las nuevas opciones del Exchange que voy a comentar en otro artículo así no hago mas largo este.  
  
En cuanto a la instalación no es muy diferente a Exchange 2007 salvo las opciones de Clustering que no lo hicimos ahora pero si entraste en la instalación Custom seguro viste qué se podía hacer y qué no. Lo diferente son algunos de los features que comenté en un artículo anterior.  
  
![image-center](/assets/images/InstalandoExchange2010sobreWindowsServer_D12D/image_15.png "Exchange 2010 Management Console"){: .align-center}      